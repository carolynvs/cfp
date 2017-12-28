# Title
Network Boot a Bare-metal Kubernetes Cluster

# Outline
* what is networking or pxe booting?
* What can you do with such a setup?
* use dnsmasq to provide pxe boot capabilities to your network
 * what is dnsmasq
 * how does it work WRT dns and pxe booting
 * considerations (hard coded ips/hostnames)
* Overview of syslinux and the OS install
* Applying scripts at the end to install kubernetes
  * customizing
  * it would be cool to kick the script automatically using an automatic reboot and runonce
* go from assembled hardware to running workloads in 10 minutes
* caveats
  * 100% unattended isn't quite there yet (bios, selecting network boot, picking options, kicking off the installation script)
  * cluster upgrades missing

# Why is this cool?
* it makes it much easier for me to setup new nodes, or start over when playing with my cluster
* are there alternatives that I should have used instead?