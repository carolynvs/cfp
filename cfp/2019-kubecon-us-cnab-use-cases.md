# Title (75)
What are Cloud Native Application Bundles and when would you use them?

## Description (900)
Cloud Native Application Bundles (CNAB) is a specification designed to help
solve some sticky problems that we all have been quietly solving in the cloud
native sphere, mostly with hope and bash. Before jumping into learning and using
CNAB, we need to think about what those problems are, admit how we are dealing
with them today (or aren't!), and get a feel for how bundles could solve them in
better ways.

Lets learn when bundles make sense, when they don't, and what your day could
look like if you were using them.

## Notes (1500)
Cloud Native Application Bundles, CNAB, is a specification recently submitted to
the Joint Development Foundation under the Linux Foundation that co-developed by
Microsoft, Pivotal, Docker, Bitnami and Hashicorp. There are several open-source
tools and libraries such as duffle, porter, docker app and cnab-go that
implement the CNAB spec.

Instead of diving into the details of the spec, or how to use one of these
tools, let's stop and consider what problems bundles can solve and when they
won't help. 

We will look at what tasks and glue scripts we are using today to tackle each of
these scenarios, what it looks like now and what the solution would look like
with bundles involved. Not just on day one with a happy path installation, but
also what it would look like after it's been in production for a while and we
need to upgrade a single component or rollback a buggy version of software.

* Version management shell game for the client tools, languages, etc required on
  the box executing installation scripts, e.g. getting the right version of
  helm, kubectl or python before you can run them to install your app
* Deploy an application along with its necessary infrastructure: cloud storage,
  dns entry, load balancer, ssl certificate.
* Get software and its dependencies into airgapped networks or offline
* Manage disparate operational tech, such as Chef, Terraform, CloudFormations,
  etc, across teams and departments without forcing standardizing.

## Bio (600)
Carolyn is a software developer based in the wilds of suburban Chicago, working
remote on the Microsoft DeisLabs team. Her passion is developer tools, and
building vibrant inclusive communities around them. She is a maintainer for
Porter, an open-source tool that builds and manages Cloud Native Application
Bundles.

In between code reviews, Carolyn enjoys hauling her cookies around the world to
share her love of open-source, containers, and excessive emoji. 🌈 ✨
