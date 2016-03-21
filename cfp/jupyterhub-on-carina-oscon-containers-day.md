# Title
JupyterHub and Carina: The Ultimate Learning Environment

# Description
Jupyter empowers you to dive right into the fun parts of problem solving. With it, you can do so much more than just your research. By combining JupyterHub with Docker, you have the ultimate learning platform, perfect for leading a workshop, trying a new language or just playing around with code. Learn how I used JupyterHub and Carina to teach others Docker, with zero setup and immediate results.

# Abstract
Jupyter is an exciting tool, empowering you to quickly dive into the fun parts of whatever problem you are solving. With it, you can do so much more than just your research. By combining JupyterHub with Docker, you have a learning platform, perfect for leading a workshop, trying a new language or just playing around with code. This provides push button user notebooks, where each user is not only isolated from others, but they are running on their own compute resources and can hit the "reset" button at any time to start fresh.

Follow along as I demonstrate how I used JupyterHub and Carina to teach others Docker, with zero setup and immediate results. Then learn how to setup your own JupyterHub instance and have user notebooks created on Carina.

# Agenda
Lay down a baseline for why we want to run JupyterHub ourselves and what's neat about connecting it to Carina. Then using HowToWhale as an example, we will walk through the infrastructure and configuration necessary to create your own on-demand user notebooks.

# Takeaway
Learn how to setup your own JupyterHub instance and have user notebooks created on Carina.

# Speaker bio
Carolyn is a software developer from Chicago, though one day she hopes to escape to the Pacific Northwest in search of faster internet, free-range kittens and respite from snow blowers. She loves all things automation, developer tools and anything that will make her fellow developers lives easier; so she's found a good home at Rackspace on the Developer Experience team where she has been developing developer tools and tutorials for Docker and Carina.

## Outline
* The inspiration behind howtowhale.com
  * howtowhale.com teaches you docker ON DOCKER
  * Inspired by tmpnb.org and CodeSchool
* Describe the howtowhale infrastructure
  * JupyterHub
  * Carina OAuth -> GitHub OAuthenticator
  * Carina Spawner -> Docker Spawner
  * User's Carina Cluster
  * Security / Tenancy
  * Tutorial Notebooks
    * Seeding users with with notebooks
* Walkthrough how to set this up from scratch for your own project
