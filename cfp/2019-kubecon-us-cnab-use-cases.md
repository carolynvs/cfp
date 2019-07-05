# Title (75)
What are Cloud Native Application Bundles and when would you use them?

## Description (900)
Cloud Native Application Bundles (CNAB) is designed to solve some sticky
problems that we all have been quietly solving in the cloud native sphere,
mostly with hope and bash.

Before we jump into learning CNAB, we should understand what those problems are,
how we are dealing with them today, and how bundles can solve them in better
ways:

* Install the tools to manage your app: helm, aws/azure/gcloud, python, terraform, etc
* Deploy an application along with its infrastructure: cloud storage, dns entry, 
  load balancer, ssl certificate, etc
* Get software and its dependencies into airgapped networks or offline
* Manage disparate operational tech, such as Chef, Terraform, CloudFormations,
  etc, across teams and departments without forcing standardizing

Let's learn when bundles make sense, when they don't, and what your day could
look like if you were using them.

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
when bundles are the right tool for the job (and when they aren't), and hopefully
thinking about learning more about making and using bundles.

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
