---
title: "Blog: Project ideas for Google Summer of Code 2023 ☀️"
date: 2025-01-03
categories: 
  - "cloud"
  - "cloudnative"
  - "devops"
  - "general"
  - "linux"
tags: 
  - "jenkins"
---

We have put together some project ideas as part of our application to participate in the Google Summer of Code 2023 program.

### 1\. CD events integration with Jenkins X

##### Description

The cdEvents project standardises the way systems talk to each other, which enables Interoperability between systems so they speak a common language through the cdEvents spec in the event. Creating a capability in Jenkins X that can receive and sent a cdEvent would benefit the project and the DevOps ecosystem in general, by stopping glue code used to integrate systems and power innovation by letting end users swap out tools with no effort.

##### Expected Outcomes

- Ability to receive cdEvents
- Ability to parse cdEvents so Jenkins X understands them
- Ability to send cdEvents

##### Recommended skills

Jenkins X, Kubernetes, golang, cdEvents

##### Mentors

- Brad McCoy

##### Resources

- https://cloudevents.io/
- https://www.youtube.com/watch?v=yg7RuDWHwV8
- https://www.jenkins.io/projects/gsoc/2021/projects/cloudevents-plugin/
- https://cdevents.dev/
- https://github.com/jenkins-x/lighthouse

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### 2\. Implement drift detection (gitops)

##### Description

Jenkins X only applies changes to cluster when contents of the gitops repository changes as part of a git pull request or git commit. This does not satisfy one of the requirements of the gitops model where we need continuous reconciliation. It would be nice to detect drift between the current state (kubernetes) and the desired state (git) and apply only those changes. This has the side effect of making the boot job faster.

Also, our bootjob is made up of a makefile which calls cli commands written in golang, instead it would be desirable to move to a controller based approach similar to other tools in the kubernetes ecosystem.

##### Expected Outcomes

- Drift detection in Jenkins X
- Configurable interval when Jenkins X will do a drift detection and apply the changes
- Updated documentation

##### Recommended skills

Kubernetes, golang, Jenkins X, kubebuiler, basic understanding of gitops.

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Resources

- https://opengitops.dev/
- https://book.kubebuilder.io/

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### 3\. RBAC (Role Based Access Control) in Jenkins X UI

##### Description

In the last GSoC project, we created a modern UI which has more functionalities than the older viewer UI. However, as we added the ability to start/stop pipelines from the new UI, this opened up an issue around access. Users of Jenkins X would like to restrict who can start/stop pipelines from the UI.

As we add more features to the UI involving repositories, this would also require ability to restrict access using RBAC (Role Based Access Control). In addition, an audit trail would also help the users keep track of activities in the UI.

##### Expected Outcomes

- Fully functional Jenkins X Dashboard running in the kubernetes cluster
- Drop in replacement for existing read only UI
- Ability to restrict access in the UI
- Audit trail of who took what action in the UI
- Updated documentation

##### Recommended skills

golang, basic understanding of sveltejs and sveltekit (or any modern js framework like react, vue. angular or solid) and kubernetes

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Resources

- https://youtu.be/AdNJ3fydeao
- https://svelte.dev/
- https://kit.svelte.dev/
- https://tailwindcss.com/
- https://go.dev/tour/welcome/1
- https://casbin.org/

##### Expected Size of project

350 hours

##### Difficulty rating

Medium

### 4\. Simplifying Jenkins X pipeline syntax

##### Description

Jenkins X uses the raw tekton pipeline syntax for pipelines. The issue with this syntax is that it’s too verbose. The verbosity makes sense for low level pipeline building libraries like tektoncd, but for an user facing tool like Jenkins X, it makes the pipeline files too big for no apparent reason. We want to investigate a new syntax which will set the boilerplate so that the syntax is recognized by tekon, but is still user friendly like gitlab/github CI.

##### Expected outcomes

- Simpler and easier to understand pipeline syntax (for developers)
- More verbose pipeline syntax for power users (if there is a need)
- Updated documentation

##### Recommended skills

Golang, kubernetes, tekton, cue

##### Resources

- https://github.com/cue-lang/cue

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Expected Size of project

350 hours

##### Difficulty rating

Medium

### 5\. Multi-tenancy in Jenkins X

##### Description

Installing multiple versions of Jenkins X in a single kubernetes cluster is not supported. There are both architectural and scalability issues around it. This would be beneficial for small teams within organizations who want to own their entire CI/CD platform instead of relying on a central release management team which can lead to more productive teams.

##### Expected outcomes

- A multi-tenant enabled Jenkins X install (jenkins X in different namespaces or a central jx install controlling pipelines running for different tenants)
- Better scaling and security model for Jenkins X
- Updated documentation

##### Recommended skills

Golang, kubernetes, event driven architecture

##### Resources

- https://github.com/jenkins-x/enhancements/pull/46

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### Next Steps

If Jenkins X gets selected, we will create a followup blog with additional details.

We have put together some project ideas as part of our application to participate in the Google Summer of Code 2023 program.

### 1\. CD events integration with Jenkins X

##### Description

The cdEvents project standardises the way systems talk to each other, which enables Interoperability between systems so they speak a common language through the cdEvents spec in the event. Creating a capability in Jenkins X that can receive and sent a cdEvent would benefit the project and the DevOps ecosystem in general, by stopping glue code used to integrate systems and power innovation by letting end users swap out tools with no effort.

##### Expected Outcomes

- Ability to receive cdEvents
- Ability to parse cdEvents so Jenkins X understands them
- Ability to send cdEvents

##### Recommended skills

Jenkins X, Kubernetes, golang, cdEvents

##### Mentors

- Brad McCoy

##### Resources

- https://cloudevents.io/
- https://www.youtube.com/watch?v=yg7RuDWHwV8
- https://www.jenkins.io/projects/gsoc/2021/projects/cloudevents-plugin/
- https://cdevents.dev/
- https://github.com/jenkins-x/lighthouse

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### 2\. Implement drift detection (gitops)

##### Description

Jenkins X only applies changes to cluster when contents of the gitops repository changes as part of a git pull request or git commit. This does not satisfy one of the requirements of the gitops model where we need continuous reconciliation. It would be nice to detect drift between the current state (kubernetes) and the desired state (git) and apply only those changes. This has the side effect of making the boot job faster.

Also, our bootjob is made up of a makefile which calls cli commands written in golang, instead it would be desirable to move to a controller based approach similar to other tools in the kubernetes ecosystem.

##### Expected Outcomes

- Drift detection in Jenkins X
- Configurable interval when Jenkins X will do a drift detection and apply the changes
- Updated documentation

##### Recommended skills

Kubernetes, golang, Jenkins X, kubebuiler, basic understanding of gitops.

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Resources

- https://opengitops.dev/
- https://book.kubebuilder.io/

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### 3\. RBAC (Role Based Access Control) in Jenkins X UI

##### Description

In the last GSoC project, we created a modern UI which has more functionalities than the older viewer UI. However, as we added the ability to start/stop pipelines from the new UI, this opened up an issue around access. Users of Jenkins X would like to restrict who can start/stop pipelines from the UI.

As we add more features to the UI involving repositories, this would also require ability to restrict access using RBAC (Role Based Access Control). In addition, an audit trail would also help the users keep track of activities in the UI.

##### Expected Outcomes

- Fully functional Jenkins X Dashboard running in the kubernetes cluster
- Drop in replacement for existing read only UI
- Ability to restrict access in the UI
- Audit trail of who took what action in the UI
- Updated documentation

##### Recommended skills

golang, basic understanding of sveltejs and sveltekit (or any modern js framework like react, vue. angular or solid) and kubernetes

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Resources

- https://youtu.be/AdNJ3fydeao
- https://svelte.dev/
- https://kit.svelte.dev/
- https://tailwindcss.com/
- https://go.dev/tour/welcome/1
- https://casbin.org/

##### Expected Size of project

350 hours

##### Difficulty rating

Medium

### 4\. Simplifying Jenkins X pipeline syntax

##### Description

Jenkins X uses the raw tekton pipeline syntax for pipelines. The issue with this syntax is that it’s too verbose. The verbosity makes sense for low level pipeline building libraries like tektoncd, but for an user facing tool like Jenkins X, it makes the pipeline files too big for no apparent reason. We want to investigate a new syntax which will set the boilerplate so that the syntax is recognized by tekon, but is still user friendly like gitlab/github CI.

##### Expected outcomes

- Simpler and easier to understand pipeline syntax (for developers)
- More verbose pipeline syntax for power users (if there is a need)
- Updated documentation

##### Recommended skills

Golang, kubernetes, tekton, cue

##### Resources

- https://github.com/cue-lang/cue

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Expected Size of project

350 hours

##### Difficulty rating

Medium

### 5\. Multi-tenancy in Jenkins X

##### Description

Installing multiple versions of Jenkins X in a single kubernetes cluster is not supported. There are both architectural and scalability issues around it. This would be beneficial for small teams within organizations who want to own their entire CI/CD platform instead of relying on a central release management team which can lead to more productive teams.

##### Expected outcomes

- A multi-tenant enabled Jenkins X install (jenkins X in different namespaces or a central jx install controlling pipelines running for different tenants)
- Better scaling and security model for Jenkins X
- Updated documentation

##### Recommended skills

Golang, kubernetes, event driven architecture

##### Resources

- https://github.com/jenkins-x/enhancements/pull/46

##### Mentors

- Ankit D Mohapatra
- Rajat Gupta

##### Expected Size of project

350 hours

##### Difficulty rating

Hard

### Next Steps

If Jenkins X gets selected, we will create a followup blog with additional details.

Go to Source
