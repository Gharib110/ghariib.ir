---
title: "Cloud native predictions for 2024 » Giant Swarm"
date: 2025-01-02
categories: 
  - "general"
---

Hard to fathom we’re already a month into 2024! With the new year comes speculation about what’s on the horizon. Peeking around the corner at what’s next is one of my favorite pastimes. But before gazing farther ahead, it's worth glancing back… In retrospect, 2023 was a transformative year. We connected IRL at KubeCon, VMware Explore, re:Invent and ContainerConf. Internally, initiatives like Giant Mansions and our much-loved Onsite powered human connections despite dispersed teams. As per my now-annual tradition of making predictions to navigate the year ahead, let’s check the rearview to see how accurate my 2023 forecasts proved before guessing what 2024 has in store.

**Revisiting 2023 predictions**

### **🔮 Companies will understand they need to build their companies for developers**

This prediction has proven to be a clear win, as evidenced by the surge in interest surrounding developer platforms. In the past, we were familiar with terms like DevOps and SRE, but the rise of Developer Platforms and Platform Services has brought a new spotlight to this area. It's not surprising, given the growing recognition that developers are the new rock stars of the tech world. Our mission at Giant Swarm aligns perfectly with this trend — we believe in empowering developers to create exceptional solutions. To achieve this, we aim to eliminate the toil associated with innovation, allowing you to focus on building great products for your customers. That's the essence of why Giant Swarm exists.

**Outcome:** 100% 

### **🔮 The new normal: global, remote, and the 32-hour workweek** 

The situation regarding remote work and office return policies remains somewhat complex. While many traditional companies with shiny office spaces are urging employees to return, a significant number of people are choosing to either ignore these calls or seek alternative employment. In this sense, I find myself both right and wrong simultaneously. The shift towards remote work is indeed the new normal, but some companies are striving to bring people back to the office.

Regarding the 32-hour workweek prediction, it's still early days, but signs of progress are promising. There are numerous articles on this topic emerging, indicating a broader shift. Germany is actually starting a scientific test around a 32-hour workweek. I recently attended an event focused on future research, and one intriguing prediction suggested that by the latter part of this century, a 20-hour workweek could become the global average.

**Outcome:** 100% accurate for the remote work aspect; early progress for the 32-hour workweek.

### **🔮 Many companies in the space will die or be "acquired" (in a fire sale)**

Things are moving slowly, with limited public information available. However, recently we already saw Nutanix buying D2IQ and Weaveworks winding down. I assume that more are struggling as innovation has made way for cost savings in these times, providing a less favorable environment for startups in the space. This is a prime time for innovation, mind you.

**Outcome:** 80% 

### **🔮 We'll adopt existing clusters**

Yes, this prediction has been realized as we've already begun adopting existing clusters, primarily focusing on EKS and AKS clusters, among others. Initially, we integrated these clusters into our management system, with plans to expand further as they become integral parts of our management cluster system. This is in line with our move to CAPI as a basis for cluster management.

**Outcome:** 100% 

### **🔮 We'll move to Discord**

Okay, this was a stretch and no we didn’t. However, we have explored the concept and even set up a demo instance. Given more time, we might consider moving parts of Giant Swarm in that direction. But for now, I must admit that this prediction stands at 0%.

**Outcome:** 0%

### **🔮 Eco-friendly hosting and cost savings**

I would rate this prediction at 80% due to our great success in running cost-saving initiatives for our customers. We've implemented various projects, including HPA, VPA, Downscaling, and Karpenter, which is now officially part of the upstream sig-autoscaling. Additionally, the emergence of companies dedicated to improving CO2 footprints aligns with the direction I discussed, emphasizing the need to enhance code quality and software development practices.

Outcome: 80%

### **🔮 Continuation of the security trend**

Despite some security companies facing challenges during the downturn, the overall trend in the industry still emphasizes the importance of security. We've witnessed great success with our Open Source security stack, reaffirming the significance of robust security measures in the ever-evolving tech landscape.

Outcome: 100%

### **Looking ahead to 2024...**

### **🔮 Decision making will be a people topic**

We’re all moving into a world where everyone has an opinion that they share and you actually want diversity because it helps make better decisions. However, how we make decisions is still unclear in this dynamic environment, especially taking into account that you need to accept that you disagree and still arrive at a meaningful conclusion. We’ll see articles, tools, and more around the subject pop up. Some will be from us.

### **🔮 CNCF will gain in strength and add key projects**

While the specific projects that will rise to prominence remain uncertain, I do know that especially with things like the VMware sale to Broadcom, companies are getting weary of relying on closed-source systems that can be ripped from under their feet at any time. They will rely more and more on Open Source implementations across various domains, empowering them to be able to stand firm on their own terms. 

**🔮 More companies or projects will fold or merge**

Last year's prediction will remain true. There will be more consolidation in the space and more pressure to generate revenues. This will lead to mergers of smaller companies or projects, acquisitions, and also companies that simply fold with no option to acquire further funding. 

### **🔮 The IDP, Internal Developer Platform trend will go full force**

The complexity surrounding Kubernetes continues to grow, especially as it does not end with Kubernetes but you are actually talking about a multitude of applications and projects that all need to be maintained, managed, and interacted with. At the same time, developers want full control over their environments, while platform teams want to provide a secure playing field that adheres to corporate standards. 

This convergence leads to the emergence of Internal Developer Platforms (IDPs) designed to streamline interactions, and we’re at the forefront, building our own IDP around Backstage.  We’re looking forward to co-innovating with our customers as we navigate this evolving terrain. 

### **🔮 GitOps becomes the standard**

Many organizations still rely on a hodgepodge of Terraform scripts to manage their fleet of clusters. However, as Kubernetes adoption grows, companies will increasingly realize the need for a Kubernetes Management Platform with full automation. This will ensure consistency across stages and provide the ability to create customized clusters for different teams.

The dream of providing small, isolated clusters for teams to test out new features and configurations has long been a goal, but the lack of automation has made this difficult to achieve. However, with the advent of IDP, GitOps, and other simplifications, this is becoming more feasible.

### **🔮 Edge clusters gain traction**

With our steadfast support for VMWare and our inaugural factory customers, we're witnessing the tangible realization of a burgeoning trend. The innovation potential in this domain is immense, with factories full of old or too little software, that allows for using IT to do energy cost savings, machine optimization, and overall process streamlining. In this context, the acronym MES, short for Manufacturing Execution System, assumes paramount importance—an encompassing and dynamic software system overseeing, monitoring, tracking, documenting, and controlling the manufacturing process from raw materials to final products. We’re excited to be collaborating with numerous customers in this realm, bolstered by great partners like MaibornWolff.

### **🔮 AI Ops is a thing**

AI is no longer confined to its initial support roles; it's rapidly expanding its influence into operations. The wealth of data at our disposal has already proven useful in optimizing postmortems and delivering cross-pollination of knowledge across seemingly disparate incidents. As systems grow in complexity and individuals become more specialized, AI emerges as a powerful tool for reestablishing a broad, panoramic view that transcends specialties.

### **🔮 Community forks for Open Source projects on the horizon**

As Open Source companies navigate the delicate balance between generating revenue and maintaining a community ethos, we foresee an increasing number making adjustments to their licenses. This shift in approach is likely to cause the emergence of at least one, possibly more, Community Versions of prominent Open Source tools. A notable example of this evolution is akin to HashiCorp's move with Terraform, which gave rise to OpenTofu.

### **🔮 Giant Swarm turns 10!**

I will get 100% on this, but this year, Giant Swarm turns 10 years old. 🤯 It's a testament to the enduring bonds we've formed and the incredible people we've had the privilege to collaborate with throughout this remarkable decade. Our capabilities today encompass a breadth and depth that surpasses anything we've achieved before.

This milestone signifies a profound evolution, transcending the realm of Kubernetes and focusing on harnessing the right CNCF toolchain to empower developers effectively. If the Lindy Effect holds true, the prospect of celebrating our 20-year anniversary looms on the horizon, and I couldn't be more thrilled.

What makes this journey truly special is that we remain in complete control of our destiny, guided by the unwavering commitment to keep our customers happy. So, to our remarkable customers, we extend our heartfelt gratitude. Thank you for your unwavering support and trust in us, enabling us to be a part of your journey towards success. 🙏

Here's to what the next 10 years may reveal!

![](https://track.hubspot.com/__ptq.gif?a=430224&k=14&r=https%3A%2F%2Fwww.giantswarm.io%2Fblog%2Fcloud-native-predictions-for-2024&bu=https%253A%252F%252Fwww.giantswarm.io%252Fblog&bvt=rss)

Go to Source
