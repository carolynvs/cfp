# A safer curl | bash for the cloud

## CNCF Tools
* Porter
* Kubernetes
* Helm
* Notary

# Abstract

Most of us have used curl to download a script and run it immediately. Using curl | bash provides instant gratification. We can quickly get up and running with an application without requiring a steep learning curve or a strong attention span. Unfortunately, the common advice is that this is not safe! But what if it was?

Let's walk through how we can work with people's natural tendencies, keep the one-liner and make it more secure. We will use Porter and Notary to transform an example cloud-native application deployment from a dicey bash script, executed with bash and hope, into a safer one-liner installation that was designed to be used in production.

You will learn:
  * Why curling a script to bash is insecure, and why bundles mitigate those risks.
  * How to reuse existing tools and scripts in a bundle, without starting over from scratch.
  * What a safer one-line user experience could look like.

# Description

Porter is a CNCF sandbox project that creates secure one-liner installations of cloud-native applications. Getting people to not do the easy thing in favor of being secure is a losing proposition. Instead of working against people's inclination, we should make the easy path also secure.

I will demonstrate packaging our app deployment with a helm chart, creating a managed database, and hosting via Cloudflare into a bundle. We will compare the curl | bash user experience to the new secure one-liner using Porter.

Highlights:
* Real world deployment of an application and its infrastructure, suitable for trying out an application or using it in production.
* Run porter explain to see deployment parameters, their defaults and what credentials are required.
* Run porter inspect to see what is inside the bundle, including referenced images and their digests.
* Sign the bundle and automatically verifying the signature against Notary during installation.

Outline at https://bit.ly/2Ry4Fyd

# Bio

Carolyn is a software developer based in the wilds of suburban Chicago, working remote on the Microsoft DeisLabs team. Her passion is developer tools, and building vibrant inclusive open-source communities around them.

Carolyn is a maintainer for Porter and the Cloud Native Application Bundle Specification. She is a technical lead for TAG Contributor Strategy.

In between code reviews, Carolyn enjoys hauling her virtual cookies around the world to share her love of Go, containers, and excessive emoji. 

# Outline
* Why we secretly like curl | bash (1m)
    * It is a one-liner to install.
    * Requires little to no knowledge of the installation logic or tooling.
    * We believe that the project maintainers can automate the installation better than us on the first try.
* Reminder on why curl | bash is unsafe (1m)
    * We don't know what the script will do.
    * Servers can detect piping to bash and swap out a malicious replacement.
    * We should be downloading the script, reading the source code, and verifying its checksum.
* Cloud-native deployments could benefit from one-liners (1m)
    * Most of us don't want to read a series of docs, and install extra tools to try something out.
    * Next we have to figure out how to script coordinating these tools. For example, creating a database, and then passing the connection string as a helm chart value.
    * Lots of people stop there and decide it is more work than they are willing to invest. Especially initially when they don't know if they want to use the software.
* Let's make those one-liners safe! (5m)
    * Flip the reflexive "You can't do that, it's not safe" to "How can we make it safe?"
    * Porter is one way have a safer one-line installer.
    * With bundles, a project can release not only its artifacts and install docs, but also a bundle that includes real-world deployment logic to deploy the application to the cloud.
    * Bundles provide a way to understand what is inside that package and safely execute it.
* Describe the demo application and its components (5m)
    * Explain that a bundle can work with any tool. It could have just as easily been serverless functions, virtual machines, etc.
    * Our demo uses:
        * A Kubernetes cluster
        * A Managed database
        * Helm charts
        * Cloudflare CDN
* Package our demo application into a bundle (5m)
    * Walk through the completed example bundle.
    * Emphasis on how to transform that mega bash script that gets piped to bash into something that exposes more metadata and is parameterized.
    * Show how Porter Mixins chain together the other tools and existing scripts. Contrast what is deployed with our bundle to what our bash installation script was deploying. Namely, an entire working deployment instead of just the application itself.
* Sign the bundle and distribute the bundle to an OCI registry and Notary (1m)
* Time to see this safer one-liner in action! (10m)
    * Show the new installation instructions for our bundle.
    * Demonstrate the safer one-liner and extra commands available to really analyze a bundle.
    * Safety First! Run porter explain to see what is in the bundle.
        * This describes the bundle and provides enough information to know how to customize the installation.
        * Shows available parameters and their defaults, e.g. exposes variables from the charts.
        * Gives a heads up on required credentials, such as cloud provider username/password and Cloudflare token.
    * Safety Second! Run porter inspect to see exactly what is inside the bundle.
        * Most people honestly don't do this (until they are in production). This is a part of the security that curl | bash lacks. Now instead of saying "read all the code and hope you understand it" key information about what is inside the bundle is easier to inspect and verify.
        * The command output lists the mixins used, such as a cloud provider's CLI, Helm, and the Cloudflare CLI.
        * Also includes images used, and their digests. The bundle's digest and digests of included images are verified by Porter when the bundle is installed.
    * Prepare to install with the porter credentials generate command, which tells Porter exactly which credentials to inject into the bundle when it installs. The bundle can't access anything unless explicitly given it.
    * Run the porter install command! This is the safer one-liner, which is in fact 2 lines at the moment.
        * Explain where the bundle is executing and what it can and more importantly cannot do. For example, even if environment variables are set with sensitive credentials such as GitHub tokens, the bundle cannot go snooping for them.
        * We can go even further and address supply chain security by verifying the signature on the bundle against Notary.
* Recap (5 min)
    * We have made the easiest thing to do also the secure thing. We are meeting our users where they are, instead of chiding them for not being more secure.
    * We are providing more fully functional default installations, instead of leaving the cloud deployment part as an exercise to the reader.
    * We are using the bundle's rich metadata to understand what is inside, so that we can vet it without wading through source code.
    * Bundle and image digests are verified automatically and with Notary signatures can be checked too.
