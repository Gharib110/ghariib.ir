---
title: "Blog: GSoC 2022 Final Report: Improving Supply Chain Security"
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

## Project Description

Supply chain security is a rising concern in the current software era. Securing the software supply chain encompasses vulnerability remediation and the implementation of controls throughout the software development process. Due to massive increase in attacks on software supply chain and the diversity of its types, Jenkins X has to make efforts to ensure that the build process is secure. As part of securing Jenkins X installation by default I worked on both securing our own components and enabling our users to use these features in their build and release steps..

## Work Done

The work done so far covers these four sections.

1. Enhancing the `jx version` output
2. Integrating with Tekton Chains to sign TaskRuns and PipelineRuns
3. Software Bill of Materials (SBOM)
4. Signing Jenkins X artifacts

### Enhancing the `jx version` output

Description:

A first step towards securing Jenkins X supply chain is to increase the amount of information gained from running `jx version` command.

Implementation

The issue created for this task is here. The PR to fix it is here.

### Integrating with Tekton Chains to sign TaskRuns and PipelineRuns

Description:

As Jenkins X uses tekton as its pipeline execution engine, `TaskRun` and `PipelineRun` are considered the key components of Jenkins X pipeline `activities` and `steps` Tekton Chains monitors the execution of all `TaskRun` and `PipelineRun` inside the cluster and takes a snapshot upon completion of each of them to sign with user-provided cryptographic keys and store them on the backend storage. The payload and signature cn be verified later using `cosign verify-blob`.

Implementation

I used the helm chart developed by Chainguard for integrating Chains with Jenkins X. To integrate the chart and added support for it on jx3-versions to make installation of helm chart easy for our users. The list of PRs for this:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx3-versions/pull/3359 | Supporting Tekton Chains helm chart with jx3-versions |
| https://github.com/jenkins-x/jx-docs/pull/3660 | Documentation on how to install and integrate Tekton Chains with Jenknins X |

NOTE: The integration is tested only on k3s cluster and work is in progress to test it on GKE and EKS.

### Software Bill of Materials (SBOM)

Description:

Software Bill Of Materials (SBOM) is a complete formally structured list of the materials (components, packages, libraries, SDK) used to build (i.e. compile, link) a given piece of software and the supply chain relationships between all these materials. It is an inventory of all the components developers used to make this software. It has many formats and many generating tools but all have the same purpose in the end.

Implementation:

I first began with investigating available standards and formats for SBOMs and tools for generating them. The results of my investigation were written to a blog post here.

I’ve settled for using syft for SBOM generation and spdx as the standard format for SBOMs. Also, I’ve added those installation as pre-defined steps in the Jenkins X pipeline catalog so it will also be available for our users to use in their pipelines and applied those steps to Jenkins X own pipelines. The list of PRs for this work are:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx/pull/8312 | Install syft using github action and generate SBOM with goreleaser |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1166 | Add Syft Installation to JX3 pipeline Catalog so it can be used to generate SBOMs |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1173 | Add Oras Steps to support pushing SBOMs as OCI artifacts |
| https://github.com/jenkins-x-plugins/jx-pipeline/pull/490 | Use Syft installation step in jx-pipeline from jx3-pipelines-catalog |
| https://github.com/jenkins-x-plugins/jx-pipeline/pull/491 | Use Oras bushing SBOMs step from jx3-pipeline-catalog |
| https://github.com/jenkins-x/jx-docs/pull/3643 | Add documentation for supporting sbom generation and storing for other jx components and our users |
| https://github.com/jenkins-x/jx/pull/8351 | Applying SBOM management to JX |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1190 | Add grype tasks for SBOM vulnerability scanning to jx3-pipeline-catalog |
| https://github.com/cdfoundation/presentations/pull/44 | Add materials for my talk with the CDF Supply Chain Securtiy SIG about SBOMs with Jenkins X |

There is also this issue to apply all steps on our active JX repositories here (WIP as there are many repositories to be updated) and the list of PRs are referenced in the issue (except those of JX because they included testing and fixing PRs at the beginning).

### Signing Jenkins X artifacts

Description:

Jenkins X is a collection of many components and tools that are used to provide the end-to-end CI/CD solution. Those components are used by our users and are also used by Jenkins X itself. It is important to sign those components to ensure the integrity of the components and the supply chain security of Jenkins X.

Implementation:

There are a set of tools developed by sigstore to sign and verify artifacts. The most used tool in my implementation is cosign. I first started with signing the Jenkins X CLI with keys stored in github secrets and then moved to signing the Jenkins X docker images. After that, I switched to use cosign keyless signing (an experimental feature using other Sigstore components (rekor and fulcio) to save end users from the hassles of key (mis)management ) The list of PRs for this work are:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx/pull/8432 | Sign goreleaser artifacts with cosign |
| https://github.com/jenkins-x/jx/pull/8441 | Sign published images with cosign |
| https://github.com/jenkins-x/jx/pull/8461 | Keyless signing for goreleaser artifacts |

## What’s next?

The work for supply chain security is still in progress and there are many things to be done. At Jenkins X, we are planning to develop new features and integrate more solutions to provide a better supply chain security for our users. The list of things to be done are:

- Add a cli subcommand in JX to verify sbom/signed binaries against the public keys.
- Add openSSF security scorecard to Jenkins X repositories.
- Integrate FRSCA work with Jenkins X.

## Acknowledgements

Out of all internships and trainings I’ve done, this one was the most challenging, rewarding and educational experience. I would like to specially thank my mentor Ankit Mohapatra for his constant support and his patience to teach me a lot of his rich knowledge he gained by experience and thank the whole team of Jenkins X for their support and guidance and for welcoming me to the community. This internship was a great experience. I had a great time working on this project and I learned a lot from it. I hope to continue contributing to Jenkins X and the open-source community in the future. Thank you.

## Project Description

Supply chain security is a rising concern in the current software era. Securing the software supply chain encompasses vulnerability remediation and the implementation of controls throughout the software development process. Due to massive increase in attacks on software supply chain and the diversity of its types, Jenkins X has to make efforts to ensure that the build process is secure. As part of securing Jenkins X installation by default I worked on both securing our own components and enabling our users to use these features in their build and release steps..

## Work Done

The work done so far covers these four sections.

1. Enhancing the `jx version` output
2. Integrating with Tekton Chains to sign TaskRuns and PipelineRuns
3. Software Bill of Materials (SBOM)
4. Signing Jenkins X artifacts

### Enhancing the `jx version` output

Description:

A first step towards securing Jenkins X supply chain is to increase the amount of information gained from running `jx version` command.

Implementation

The issue created for this task is here. The PR to fix it is here.

### Integrating with Tekton Chains to sign TaskRuns and PipelineRuns

Description:

As Jenkins X uses tekton as its pipeline execution engine, `TaskRun` and `PipelineRun` are considered the key components of Jenkins X pipeline `activities` and `steps` Tekton Chains monitors the execution of all `TaskRun` and `PipelineRun` inside the cluster and takes a snapshot upon completion of each of them to sign with user-provided cryptographic keys and store them on the backend storage. The payload and signature cn be verified later using `cosign verify-blob`.

Implementation

I used the helm chart developed by Chainguard for integrating Chains with Jenkins X. To integrate the chart and added support for it on jx3-versions to make installation of helm chart easy for our users. The list of PRs for this:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx3-versions/pull/3359 | Supporting Tekton Chains helm chart with jx3-versions |
| https://github.com/jenkins-x/jx-docs/pull/3660 | Documentation on how to install and integrate Tekton Chains with Jenknins X |

NOTE: The integration is tested only on k3s cluster and work is in progress to test it on GKE and EKS.

### Software Bill of Materials (SBOM)

Description:

Software Bill Of Materials (SBOM) is a complete formally structured list of the materials (components, packages, libraries, SDK) used to build (i.e. compile, link) a given piece of software and the supply chain relationships between all these materials. It is an inventory of all the components developers used to make this software. It has many formats and many generating tools but all have the same purpose in the end.

Implementation:

I first began with investigating available standards and formats for SBOMs and tools for generating them. The results of my investigation were written to a blog post here.

I’ve settled for using syft for SBOM generation and spdx as the standard format for SBOMs. Also, I’ve added those installation as pre-defined steps in the Jenkins X pipeline catalog so it will also be available for our users to use in their pipelines and applied those steps to Jenkins X own pipelines. The list of PRs for this work are:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx/pull/8312 | Install syft using github action and generate SBOM with goreleaser |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1166 | Add Syft Installation to JX3 pipeline Catalog so it can be used to generate SBOMs |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1173 | Add Oras Steps to support pushing SBOMs as OCI artifacts |
| https://github.com/jenkins-x-plugins/jx-pipeline/pull/490 | Use Syft installation step in jx-pipeline from jx3-pipelines-catalog |
| https://github.com/jenkins-x-plugins/jx-pipeline/pull/491 | Use Oras bushing SBOMs step from jx3-pipeline-catalog |
| https://github.com/jenkins-x/jx-docs/pull/3643 | Add documentation for supporting sbom generation and storing for other jx components and our users |
| https://github.com/jenkins-x/jx/pull/8351 | Applying SBOM management to JX |
| https://github.com/jenkins-x/jx3-pipeline-catalog/pull/1190 | Add grype tasks for SBOM vulnerability scanning to jx3-pipeline-catalog |
| https://github.com/cdfoundation/presentations/pull/44 | Add materials for my talk with the CDF Supply Chain Securtiy SIG about SBOMs with Jenkins X |

There is also this issue to apply all steps on our active JX repositories here (WIP as there are many repositories to be updated) and the list of PRs are referenced in the issue (except those of JX because they included testing and fixing PRs at the beginning).

### Signing Jenkins X artifacts

Description:

Jenkins X is a collection of many components and tools that are used to provide the end-to-end CI/CD solution. Those components are used by our users and are also used by Jenkins X itself. It is important to sign those components to ensure the integrity of the components and the supply chain security of Jenkins X.

Implementation:

There are a set of tools developed by sigstore to sign and verify artifacts. The most used tool in my implementation is cosign. I first started with signing the Jenkins X CLI with keys stored in github secrets and then moved to signing the Jenkins X docker images. After that, I switched to use cosign keyless signing (an experimental feature using other Sigstore components (rekor and fulcio) to save end users from the hassles of key (mis)management ) The list of PRs for this work are:

| PR | Short Description |
| --- | --- |
| https://github.com/jenkins-x/jx/pull/8432 | Sign goreleaser artifacts with cosign |
| https://github.com/jenkins-x/jx/pull/8441 | Sign published images with cosign |
| https://github.com/jenkins-x/jx/pull/8461 | Keyless signing for goreleaser artifacts |

## What’s next?

The work for supply chain security is still in progress and there are many things to be done. At Jenkins X, we are planning to develop new features and integrate more solutions to provide a better supply chain security for our users. The list of things to be done are:

- Add a cli subcommand in JX to verify sbom/signed binaries against the public keys.
- Add openSSF security scorecard to Jenkins X repositories.
- Integrate FRSCA work with Jenkins X.

## Acknowledgements

Out of all internships and trainings I’ve done, this one was the most challenging, rewarding and educational experience. I would like to specially thank my mentor Ankit Mohapatra for his constant support and his patience to teach me a lot of his rich knowledge he gained by experience and thank the whole team of Jenkins X for their support and guidance and for welcoming me to the community. This internship was a great experience. I had a great time working on this project and I learned a lot from it. I hope to continue contributing to Jenkins X and the open-source community in the future. Thank you.

Go to Source
