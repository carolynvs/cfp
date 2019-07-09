# Title (75)
Cloud Native Applications are more than just Kubernetes, deal with it!

## Description (900)
Can you deploy your entire app from scratch with a Helm install? Or do you
have cloud infra and hosted services that you rely on? The cloudy bits that make
your app cloud native.

Cloud Native Application Bundles, the jointly developed CNAB spec, was designed
to solve deployment problems that we all have been quietly solving, mostly with
hope and bash. CNAB comes in handy when dealing with applications that don't
live neatly inside of just Kubernetes.

Let's learn when bundles make sense, when they don't, and what your day could
look like if you were using them:

* Install the tools to manage your app: helm, aws/azure/gcloud, terraform
* Deploy an app along with its infra: cloud storage, dns entry, load balancer, ssl cert
* Get software and its dependencies into airgapped networks
* Manage disparate operational tech, such as Chef, Terraform, CloudFormations, across teams and departments

## Notes (1500)
Cloud Native Application Bundles, CNAB, is a specification recently submitted to
the Joint Development Foundation under the Linux Foundation, co-developed by
Microsoft, Pivotal, Docker, Bitnami and Hashicorp. There are several open-source
tools and libraries such as duffle, porter, docker app and cnab-go that
implement the CNAB spec.

Instead of diving into the details of the spec, or how to use one of these
tools, I want to help people understand the types of problems CNAB solves, and
what it would look like before and after bundles were introduced into their
stack. The goal is for people to leave with an understanding of what CNAB is,
when bundles are the right tool for the job, when they aren't, and inspire
people to learn more about making and using bundles.

CNAB is relevant to CloudNativeCon because it is a specification designed to 
operate cloud native applications, agnostic of any particular cloud or tooling.
It can be used to manage cloud infrastructure, a kubernetes cluster, cloud native
applications, and works well with tooling like Helm, Terraform, etc.

## Bio (600)
Carolyn is a software developer based in the wilds of suburban Chicago, working
remote on the Microsoft DeisLabs team. Her passion is developer tools, and
building vibrant inclusive communities around them. She is a maintainer for
Porter, an open-source tool that builds and manages Cloud Native Application
Bundles.

In between code reviews, Carolyn enjoys hauling her cookies around the world to
share her love of open-source, containers, and excessive emoji. 🌈 ✨

### Outline

If you can deploy your cloud native app without any cloud infrastructure
or hosted services, is it really cloud native? 😂