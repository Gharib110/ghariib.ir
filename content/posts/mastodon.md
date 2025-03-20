---
title: "Run Private Mastodon Instance"
date: 2024-09-10
draft: false
type: posts
categories:
  - Mastodon, Federation
tags:
  - mastodon, federation
summary: "How to run a Private Mastodon Instance ?"
---
This guide helps you to run a private Mastodon Instance.
I personally prefer to use mastodon with docker and docker-compose to isolate my application from main server environment.
The following docker compose yaml file helps you to deploy your instance. After that we try to modify the settings of our application to make it private instance (Personal Instance with just One Account).
Put the content of the following docker-compose config into a seperate folder.
```yaml
# This file is designed for production server deployment, not local development work
# For a containerized local dev environment, see: https://github.com/mastodon/mastodon/blob/main/README.md#docker

services:
  db:
    restart: always
    image: postgres:14-alpine
    shm_size: 256mb
    networks:
      - internal_network
    healthcheck:
      test: ['CMD', 'pg_isready', '-U', 'postgres']
    volumes:
      - ./mastodon/postgres14:/var/lib/postgresql/data
    environment:
      - 'POSTGRES_HOST_AUTH_METHOD=trust'
      - 'POSTGRES_USER=mastodon'
      - 'POSTGRES_DB=mastodon'
      - 'POSTGRES_PASSWORD=pasword'

  redis:
    restart: always
    image: redis:7-alpine
    networks:
      - internal_network
    healthcheck:
      test: ['CMD', 'redis-cli', 'ping']
    volumes:
      - ./mastodon/redis:/data

  # es:
  #   restart: always
  #   image: docker.elastic.co/elasticsearch/elasticsearch:7.17.4
  #   environment:
  #     - "ES_JAVA_OPTS=-Xms512m -Xmx512m -Des.enforce.bootstrap.checks=true"
  #     - "xpack.license.self_generated.type=basic"
  #     - "xpack.security.enabled=false"
  #     - "xpack.watcher.enabled=false"
  #     - "xpack.graph.enabled=false"
  #     - "xpack.ml.enabled=false"
  #     - "bootstrap.memory_lock=true"
  #     - "cluster.name=es-mastodon"
  #     - "discovery.type=single-node"
  #     - "thread_pool.write.queue_size=1000"
  #   networks:
  #      - external_network
  #      - internal_network
  #   healthcheck:
  #      test: ["CMD-SHELL", "curl --silent --fail localhost:9200/_cluster/health || exit 1"]
  #   volumes:
  #      - ./elasticsearch:/usr/share/elasticsearch/data
  #   ulimits:
  #     memlock:
  #       soft: -1
  #       hard: -1
  #     nofile:
  #       soft: 65536
  #       hard: 65536
  #   ports:
  #     - '127.0.0.1:9200:9200'

  web:
    # You can uncomment the following line if you want to not use the prebuilt image, for example if you have local code changes
    # build: .
    image: ghcr.io/mastodon/mastodon:v4.2.12
    restart: always
    env_file: .env.production
    command: bundle exec puma -C config/puma.rb
    networks:
      - external_network
      - internal_network
    healthcheck:
      # prettier-ignore
      test: ['CMD-SHELL',"curl -s --noproxy localhost localhost:3000/health | grep -q 'OK' || exit 1"]
    ports:
      - '127.0.0.1:3000:3000'
    depends_on:
      - db
      - redis
      # - es
    volumes:
      - ./mastodon/public/system/:/mastodon/public/system

  streaming:
    # You can uncomment the following lines if you want to not use the prebuilt image, for example if you have local code changes
    # build:
    #   dockerfile: ./streaming/Dockerfile
    #   context: .
    image: ghcr.io/mastodon/mastodon-streaming:latest
    restart: always
    env_file: .env.production
    command: node ./streaming/index.js
    networks:
      - external_network
      - internal_network
    healthcheck:
      # prettier-ignore
      test: ['CMD-SHELL', "curl -s --noproxy localhost localhost:4000/api/v1/streaming/health | grep -q 'OK' || exit 1"]
    ports:
      - '127.0.0.1:4000:4000'
    depends_on:
      - db
      - redis

  sidekiq:
    build: .
    image: ghcr.io/mastodon/mastodon:v4.2.12
    restart: always
    env_file: .env.production
    command: bundle exec sidekiq
    depends_on:
      - db
      - redis
    networks:
      - external_network
      - internal_network
    volumes:
      - ./mastodon/public/system/:/mastodon/public/system/
    healthcheck:
      test: ['CMD-SHELL', "ps aux | grep '[s]idekiq\ 6' || false"]

  ## Uncomment to enable federation with tor instances along with adding the following ENV variables
  ## http_hidden_proxy=http://privoxy:8118
  ## ALLOW_ACCESS_TO_HIDDEN_SERVICE=true
  # tor:
  #   image: sirboops/tor
  #   networks:
  #      - external_network
  #      - internal_network
  #
  # privoxy:
  #   image: sirboops/privoxy
  #   volumes:
  #     - ./priv-config:/opt/config
  #   networks:
  #     - external_network
  #     - internal_network

networks:
  external_network:
  internal_network:
    internal: true
```
The ``.env.prodution`` file store critical information about your instance.
It is better to use password with your redis instance.
```bash
DB_HOST=db
DB_PORT=5432
DB_NAME=mastodon
DB_USER=mastodon
DB_PASS=password
REDIS_HOST=redis
REDIS_PORT=6379
REDIS_PASSWORD=
```
Run ``docker-compose run --rm web bundle exec rake mastodon:setup`` in the folder which holds ``docker-compose.yml`` then follow the instructions and answer the questions.

Run the following commands to create a user and make it admin.
```bash
export RAILS_ENV=production tootctl accounts create --email EMAIL --confirmed --role Admin
export RAILS_ENV=production tootctl accounts modify USERNAME --approve
export RAILS_ENV=production tootctl accounts approve USERNAME
```
The commands above give you the requirement information to login to your server.

I prefer using nginx to expose my instance to the internet.
```bash
map $http_upgrade $connection_upgrade {
  default upgrade;
  ''      close;
}

upstream backend {
    server 127.0.0.1:3000 fail_timeout=0;
}

upstream streaming {
    # Instruct nginx to send connections to the server with the least number of connections
    # to ensure load is distributed evenly.
    least_conn;

    server 127.0.0.1:4000 fail_timeout=0;
    # Uncomment these lines for load-balancing multiple instances of streaming for scaling,
    # this assumes your running the streaming server on ports 4000, 4001, and 4002:
    # server 127.0.0.1:4001 fail_timeout=0;
    # server 127.0.0.1:4002 fail_timeout=0;
}

proxy_cache_path /var/cache/nginx levels=1:2 keys_zone=CACHE:10m inactive=7d max_size=1g;

server {
  listen <IP>:80;
  server_name domain.com;
  root /var/www/mastodon/public;
  location /.well-known/acme-challenge/ { allow all; }
  location / { return 301 https://$host$request_uri; }
}

server {
  listen <IP>:443 ssl http2;
  server_name domain.com;

  ssl_protocols TLSv1.2 TLSv1.3;
  ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384:DHE-RSA-CHACHA20-POLY1305;

  ssl_prefer_server_ciphers on;
  ssl_session_cache shared:SSL:10m;
  ssl_session_tickets off;
  access_log /var/log/nginx/mastodonaccess.log;
  error_log /var/log/nginx/mastodonerror.log warn;
  
  ssl_certificate /root/ghariib.ir.crt;
  ssl_certificate_key /root/ghariib.ir.key;

  keepalive_timeout 70;
  sendfile on;
  client_max_body_size 99m;

  root /var/www/mastodon/public;

  gzip on;
  gzip_disable "msie6";
  gzip_vary on;
  gzip_proxied any;
  gzip_comp_level 6;
  gzip_buffers 16 8k;
  gzip_http_version 1.1;
  gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript image/svg+xml image/x-icon;

  location / {
    try_files $uri @proxy;
  }

  location = /sw.js {
    add_header Cache-Control "public, max-age=604800, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/assets/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/avatars/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/emoji/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/headers/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/packs/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/shortcuts/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/sounds/ {
    add_header Cache-Control "public, max-age=2419200, must-revalidate";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    try_files $uri =404;
  }

  location ~ ^/system/ {
#    root /root/mastodon/public/system;  # New root path for /system/
    add_header Cache-Control "public, max-age=2419200, immutable";
    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";
    add_header X-Content-Type-Options nosniff;
    add_header Content-Security-Policy "default-src 'none'; form-action 'none'";
    try_files $uri =404;
  }

  location ^~ /api/v1/streaming {
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header Proxy "";

    proxy_pass http://streaming;
    proxy_buffering off;
    proxy_redirect off;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection $connection_upgrade;

    add_header Strict-Transport-Security "max-age=63072000; includeSubDomains";

    tcp_nodelay on;
  }

  location @proxy {
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
    proxy_set_header Proxy "";
    proxy_pass_header Server;

    proxy_pass http://backend;
    proxy_buffering on;
    proxy_redirect off;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection $connection_upgrade;

    proxy_cache CACHE;
    proxy_cache_valid 200 7d;
    proxy_cache_valid 410 24h;
    proxy_cache_use_stale error timeout updating http_500 http_502 http_503 http_504;
    add_header X-Cached $upstream_cache_status;

    tcp_nodelay on;
  }

  error_page 404 500 501 502 503 504 /500.html;
}
```
