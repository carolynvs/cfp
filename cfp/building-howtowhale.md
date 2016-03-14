# Title
Building the ultimate learning environment with Docker

# Abstract (200 words)
Docker is an exciting platform for running your application in production, but
did you know that it can provide a better experience for your customers too? Give them
a taste of your application with a personalize demo,
jump-start the learning process with an interactive tutorial
or bring your online documentation to life with live examples.

Learn how howtowhale.com uses JupyterHub and Carina to teach Docker,
with zero setup and immediate results. These are essential building blocks that
you can use to build the ultimate learning environment for your customers.

# Outline
First, we will answer why Docker is a great fit for demos, tutorials and documentation.
Next using howtowhale.com as an example, we will walk through the infrastructure
and configuration necessary to create your own interactive, sandboxed user environments.
Then we will do a quick demo of how to build a magic button that sets up your
application for your customers.

# Takeaways
* Come away with three ways to use Docker in non-traditional environments
* See what goes into building on-demand interactive, isolated sandboxes for your customers
* Download source code for working examples that you can build upon and customize

# Tags
1. learning
2. jupyterhub
3. carina

# Speaker bio
Carolyn is a software developer from Chicago, though one day she hopes
to escape to the Pacific Northwest in search of faster internet, free-range kittens
and respite from snow blowers. She loves all things automation, developer tools
and anything that will make her fellow developers lives easier; so she's found a good home
at Rackspace on the Developer Experience team where she has been developing
developer tools and tutorials for Docker and Carina.


## Outline (details)
* Docker is the perfect sandbox for demos
  * It's not uncommon to see a gif showing how something works
  * Even better is a live demo
  * But many demos dump you in a shared environment that is wiped regularly
  * With docker we can give each user a demo environment
* This applies to workshops and live online documentation as well
  * howtowhale.com teaches you docker ON DOCKER
  * Inspired by tmpnb.org and CodeSchool
  * Setup live doc for Rackspace.NET
* Why howtowhale?
  * List milestones in learning Docker
    * Know it exists (check!)
    * Know how you would use it (erm...)
    * Install it on your machine (oh boy...)
      * Docker Toolbox is amazing but it can still be a rocky setup with common missteps, especially for Windows users
      * oh I guess I need to learn bash too right now
      * learn docker-machine, before I can learn docker
  * I want to teach someone docker with zero investment on their part
    * zero setup
    * we provide the use cases
    * the environment sticks around so they can start today, get distracted by life for a month, and come back
* Describe the howtowhale infrastructure
  * JupyterHub
  * Carina OAuth -> GitHub OAuthenticator
  * Carina Spawner -> Docker Spawner
  * User's Carina Cluster
  * Security / Tenancy
  * Docker connection
  * Tutorial Notebooks
    * How does a Jupyter notebook work
* Making your own Try Foo
  * Doesn't require the user to know docker at all
  * Walk through how to do the same thing, e.g. a button to setup word press for the user
