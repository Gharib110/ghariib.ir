---
title: "Downloading the same file 102+ times"
date: 2025-01-08
tags: 
  - "browser"
  - "file"
  - "go"
  - "ui"
  - "un"
---

Have YOU ever tried downloading the same file 102+ times in your favorite browser? Do you know what happens on the 102nd time? 🙃

I do. The answer is ... it depends 😋 It varies between browsers and it’s a bit of a surprise.

Before I show you the screenshots, let me first tell you a short story about how I ended up in the _“lets-download-this-file-102-times”_ rabbit hole so bear with me.

I work as a software developer and one day I got a message from a colleague asking something about a new feature. She sent me a link to an issue. There was a screenshot that caught my attention. It looked very much like the one below.

![List of recently downloaded files similar to the screenshot in our project](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fm7j9bf4e7isba9hzuyvf.png)

At the time the file’s name was hardcoded to _“Report.zip”_. So seeing _“Report.zip”_, _“Report (1).zip”_ or _“Report (42).zip”_ was to be expected. Instead of a counter, I was suprised to see a timestamp. Where did that come from? It was absolutely not in the code. My colleague didn’t manually add it either. Something was not right. And from here on the rabbit hole got deeper and deeper. 🐰

_“A browser setting!”_ - I thought. It was rulled out quite quickly because she didn’t remember changing any settings. We were looking in Edge because that’s the browser she uses. Besides, such a setting does not exist, I later found out.

_“Well, then maybe the browser added it automatically. But at what point?”_ I started searching on Google, going through different web pages, StackOverflow posts and forums. The more I searched, the more curious I became to figure this out. Then finally - FINALLY - a reply to a Reddit post gave me a pretty strong hint.

But was that still the case? There was only one way to find out. 🚀

Fired up Edge and started downloading.

1, 2, 3, ... 10, ... 42, ... 99 times.

Then something magical 🪄 happened the 102nd time! Instead of bumping a number, Edge added a timestamp 😯 Bingo! 🎉 The mystery was solved. That explained it.

So to make this more scientific, and for the purpose of this post, I decided to repeat the exercise in other browsers. Here are some screenshots.

### Edge

![Downloading the same file 102+ times in Edge](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2F85kfcntccavv62raz8tw.png)

### Chrome

![Downloading the same file 102+ times in Chrome. Same as Edge](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2F249jsuw3lmritxmnag72.png)

### Firefox

Firefox just continues with bumping the counter. No timestamp here. Also note that there’s no space between the file’s name and the counter in parenthesis, as is the case in Edge/Chrome.

![Downloading the same file 102+ times in Firefox](https://media2.dev.to/dynamic/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fyqmb8h89ge1op48sntkl.png)

What a TIL!

Thanks for reading thus far. Hope you learned something new. See you in another post 😊

P.S. If you want to try it yourself, I’ve prepared a zip with an empty text file. Go ahead and download it. 102 times, of course.

Or you can quickly put together a simple demo by linking to a local file.  

```
<a href="./fancy.zip" download>Download</a>
```

Go to Source
