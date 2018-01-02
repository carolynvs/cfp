# Title
DIY Home Netflix

# Description
Are you looking for an excuse to try Kubernetes? How about converting your DVD collection into a DIY Home Netflix! If you have at least one computer lying around, you have enough horsepower to build a Kubernetes cluster and put it to good use.

Starting from only a basic understanding of Kubernetes, learn how to:
* Build out a Kubernetes cluster at home
* Transcode discs into a digital format using HandBrake
* Install HandBrk8s on your cluster to transcode multiple videos at once
* Watch your movies from your TV, just like Netflix

The payoff? Never having to get off the couch to put in a disc ever again.

# Misc
Carolyn is the author of HandBrk8s, HandBrake on Kubernetes, and is also the proud owner of her very own My Little Pony cluster which has taken over her guest bedroom. She will walk through how HandBrk8s takes advantage of Kubernetes to simplify resiliantly transcoding DVDs on a cluster.

# Outline
handbrk8s
* what do you need in order to do your own at home netflix?
  * something to run the plex server on (k8s itself or a nas)
  * plex client (tv, roku, tivo)
  * cluster to perform the encoding
  * disk space and time requirements
* live demo of my home setup
* how does transcoding work?
  * highlight how handbrake works via the GUI
  * presets
  * useful settings you may want to tweak
* small detour into my attempts at building handbrk8s
  * why this is a great example of naievely porting something to microservices k8s
  * adventures in side projects and finding an excuse to use k8s
* walkthrough handbrk8s components
  * handbrake cli
  * watcher
  * k8s jobs
  * config / job templates
  * job chaining
  * init containers
  * uploader
* beyond
    * what's still broken?
    * What fun stuff is left to do?
* call to action
  * try with minikube and a video sample
  * get something to work, and make it cooler over time