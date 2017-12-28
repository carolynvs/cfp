# Title
DIY Home Netflix

# Abstract
Looking for an excuse to use Kubernetes? How about converting your DVD collection into a DIY Home Netflix! If you have at least one computer lying around, you have enough horsepower to build a home Kubernetes cluster and put it to good use.

With only a basic understanding of Kubernetes, learn how to:
* Build out a Kubernetes cluster on your home computers
* Transcode DVDs into a digital format for playback using HandBrake
* Install HandBrk8s on your cluster to transcode multiple DVDs at once
* Watch your movies from your TV, just like Netflix

Carolyn is the author of HandBrk8s, HandBrake on Kubernetes, and the proud owner of her very own My Little Pony cluster. She will walk through how it takes advantage of Kubernetes to simplify resiliantly transcoding DVDs on a cluster. The payoff? Never again having to get off the couch to put in a DVD.

# Outline
handbrk8s
* what do you need in order to do your own at home netflix?
  ** nas, plex client
  ** cluster to encode
* how does transcoding work?
    * my settings
* my first attempt
* why this is a great example of naievely porting something to microservices k8s
* my second attempt
* walkthrough components
  * handbrake cli
  * watcher
  * k8s jobs
  * job chaining
  * init containers
  * uploader
* pushing state into k8s
* beyond
    * what's still broken?
    * What fun stuff is left to do?
