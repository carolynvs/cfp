# Title
Cloud Portability Starts At Localhost

# Abstract

# Outline
* often what it takes to run an app in production looks different than in dev. We end up with scripts and shims to make it work.
* It's usually not the stateless apps that cause this, it's depenencies on other services and infrastructure
* service catalog will help with some parts
* draft packs will help with others (so you aren't dealing with svc-cat directly)


LAMP app
 - use draft to bootstrap
 - run it on minikube
 - live change code
 - deploy to prod
 - no custom scripts
 - use monocular to do this from a website with big pretty buttons
  - need svc-cat enabled draft packs
  - need upstream helm charts with svc-cat support