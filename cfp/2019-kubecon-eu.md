# Title

Cloud Native Package Management with Porter

# Abstract

When we deploy to the cloud, most of us aren't dealing with just a single cloud provider or even deployment tool. 
It seems like even the simplest of applications today need nginx, Let's Encrypt, persistent file storage, DNS, and 
somewhere in there your application. 

That is a lot to figure out! Porter, a cloud native package manager built on CNAB, helps you manage everything into a 
single package and focus on what you know best: your application. Learn how Porter makes it easier to manage cloud native 
applications in the messy imperfect hybrid cloud world that we all live in. 

# Submission Notes / Outline

* Discuss problems that a Cloud Native package manager should solve
    * Share how we borrowed ideas from existing tools like Chef and Helm.
    * Explore a desireable developer experience: composability, don't assume you are the only part of the ecosystem, 
    or that users know what they are doing.
* Introduce Porter (https://github.com/deislabs/porter)
* Brief overview of Cloud Native Application Bundles (CNAB)
    * See https://cnab.io to learn more about the CNAB spec
    * CNAB isn't a Microsoft project and is going to be accepted into the Open Containers Initiative (OCI).
* Demo: Deploying Sentiment Analysis Application (of the #KubeCon tweets tag) using Porter
    * K8s on a on-stage NUC (simulate on-premise datacenter)
    * Azure Cloud Services (so we can demonstrate hybrid cloud problems)
    * Helm
* Anatomy of a Porter bundle by walking through the Porter manifest for the demo bundle
* Encourage people to contribute bundles and mixins