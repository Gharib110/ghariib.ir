---
title: "Blog: Kubernetes 1.22 - Breaking change!"
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

To allow Jenkins X to support Kubernetes 1.22, we had to update our version of Tekton. This updated version of Tekton contains breaking changes that has consequences if you made your own custom Jenkins X pipelines.

To make sure that your custom pipelines continue to work after this upgrade, you must edit the resource settings in your pipelines. Otherwise your pipelines will most likely not be able to start at all, or if they do, consume a lot of resources.

#### Changes in Tekton version 28

Tekton made changes in how to calculate the resources needed to run a pipeline, in order to support the concept of LimitRange in Kubernetes (introduced in Kubernetes version 1.10). Previously, Tekton simply used the maximum requested cpu and memory of any single step, and set that as limits for the all steps in the pipeline.

For more details, please read the Tekton documentation on LimitRange.

#### How to prepare for upgrade

In the Tekton pipeline files, the StepTemplate needs to be changed to not specify resource `requests`, but only setting an empty resource `limits`:

```yaml
stepTemplate:
  image: uses:jenkins-x/jx3-pipeline-catalog/tasks/go/release.yaml@a5ab19ebc5a074e0402c5016b11bc11b32cc5c83
  name: ""
  resources:
    # override limits for all containers here
    limits: {}
```

The resource `requests` should be set on only one individual step:

```yaml
steps:
  - image: uses:Mentor-Medier/jx3-pipeline-catalog/tasks/git-clone/git-clone-pr.yaml@versionStream
    name: ""
    resources: {}
  - name: jx-variables
    resources:
      requests:
        cpu: 400m
        memory: 512Mi
```

To see examples of what changes you need to apply to your custom pipelines you may investigate this PR on The Jenkins X pipeline catalog. The PR will be merged and released simultaneous with the upgrade of Tekton.

In the current version of Tekton used by Jenkins X, the resource `requests` are set on the stepTemplate. Running the old pipelines in the new version will lead to resource `requests` being multiplied by the number of steps.

To prepare for upgrade, you should create a PR applying the changes described above. We done some tests on applying the changes to the current version of Jenkins X/Tekton, and it seemed to work. But - that does not mean it will work on your machines or even pipelines!

So, please prepare for upgrade now! We want people to have a safe upgrade experience. If you have questions, you can find us on Slack.

To allow Jenkins X to support Kubernetes 1.22, we had to update our version of Tekton. This updated version of Tekton contains breaking changes that has consequences if you made your own custom Jenkins X pipelines.

To make sure that your custom pipelines continue to work after this upgrade, you must edit the resource settings in your pipelines. Otherwise your pipelines will most likely not be able to start at all, or if they do, consume a lot of resources.

#### Changes in Tekton version 28

Tekton made changes in how to calculate the resources needed to run a pipeline, in order to support the concept of LimitRange in Kubernetes (introduced in Kubernetes version 1.10). Previously, Tekton simply used the maximum requested cpu and memory of any single step, and set that as limits for the all steps in the pipeline.

For more details, please read the Tekton documentation on LimitRange.

#### How to prepare for upgrade

In the Tekton pipeline files, the StepTemplate needs to be changed to not specify resource `requests`, but only setting an empty resource `limits`:

```yaml
stepTemplate:
  image: uses:jenkins-x/jx3-pipeline-catalog/tasks/go/release.yaml@a5ab19ebc5a074e0402c5016b11bc11b32cc5c83
  name: ""
  resources:
    # override limits for all containers here
    limits: {}
```

The resource `requests` should be set on only one individual step:

```yaml
steps:
  - image: uses:Mentor-Medier/jx3-pipeline-catalog/tasks/git-clone/git-clone-pr.yaml@versionStream
    name: ""
    resources: {}
  - name: jx-variables
    resources:
      requests:
        cpu: 400m
        memory: 512Mi
```

To see examples of what changes you need to apply to your custom pipelines you may investigate this PR on The Jenkins X pipeline catalog. The PR will be merged and released simultaneous with the upgrade of Tekton.

In the current version of Tekton used by Jenkins X, the resource `requests` are set on the stepTemplate. Running the old pipelines in the new version will lead to resource `requests` being multiplied by the number of steps.

To prepare for upgrade, you should create a PR applying the changes described above. We done some tests on applying the changes to the current version of Jenkins X/Tekton, and it seemed to work. But - that does not mean it will work on your machines or even pipelines!

So, please prepare for upgrade now! We want people to have a safe upgrade experience. If you have questions, you can find us on Slack.

Go to Source
