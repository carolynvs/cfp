# Title

Welcoming Windows to the neighborhood: Writing cross-platform first applications

# Abstract

If you spend most of your day in the Mac / Linux world, you may not realize this but
there are a lot of Windows developers moving into your neighborhood. Windows
developers may have used to work in isolation, but not anymore thanks to the popularity of
git, node and Docker. Not only is Microsoft embracing open source,
but enterprises are finally allowing their developers to use open source libraries and tools.

But here's the rub: many useful tools are still written "Unix first",
half-heartedly shoehorning in Windows support later and that is turning away potential users.
Which is a shame! Lucky for us, Go has amazing support for cross-platform development
which we can use to welcome our Windows neighbors by writing cross-platform first.

Suitable for beginners and Go gurus alike. Learn some of the Windows quirks
that you should take into account, and the Go goodies that will help you
conquer them.

# Speaker bio
Carolyn is a software developer from Chicago, though one day she hopes
to escape to the Pacific Northwest in search of faster internet, free-range kittens
and respite from snow blowers. She loves all things automation, developer tools
and anything that will make her fellow developers lives easier; so she's found a good home
at Rackspace on the Developer Experience team. Like a grafted bonsai,
her roots come from many places: happily developing C# applications on a Mac and deploying to Linux.

## Agenda
40 minutes, 10 minutes for questions

* Speaker and Topic Introduction - 5 minutes
* Cross-platform tools at Rackspace - 5 minutes
* Rewriting the Docker Version Manager - 10 minutes
* Adding Windows Support to Carina CLI - 5 minutes
* Cross-platform Build Tips - 5 minutes
* Cross-platform Testing Tips - 5 minutes
* Summary / Cheat Sheet - 5 minutes

# Proposal Extras

## Tags
cross-platform windows go

## What's the takeaway for the audience?
We can do better! By keeping a few things in mind, we can develop cross-platform
applications that embrace a wider community.

## Prerequisite knowledge for this presentation
None!

## Outline
* Introduction
  * I'm a mongrel developer. I started with linux, get paid to develop C# for Windows, and do it all on a Mac. Which funny enough, is not really all that rare anymore.
  * Where are these Windows devs coming from? What do they want?

* Backstory
  * Cranking as fast as possible towards releasing a new product, Carina. We had some tools to go along with it (dvm and carina cli)
and wanted to provide a great experience for all developers, regardless of OS.
  * DVM was a bash script. It could not get more nix first.
  * Carina was written in Go, but the developer didn't know what to look out for when supporting Windows. So really it was nix only too.
  * From my experiences with building and testing docker machine, I knew that Go works really well for cross-platform CLIs. I decided to learn Go and use that to rewrite dvm.

* Rewriting the Docker Version Manager
  * The process of converting a bash script to go isn't terribly interesting.
  * The fun part was figuring out how to communicate between go and the current shell session, such as updating the PATH variable... on each OS.
  * Windows has more than one shell! Thanks to most Windows devs having git installed, bash is avilable, along with cmd and powershell. Not a concern for Go directly, but it's part of the ecosystem.

* Adding Windows support to Carina CLI
  * Already in Go! Huzzah!
  * What we needed was some judicious use of environment variables, e.g. where is the home dir on each os, and using path/filepath.
  * Occasionally making use of conditional compilation.

* Building
  * went with make
  * 'make' builds for your current os
  * run a cross build during ci
  * How to get make on windows, what you can reasonably expect a windows dev to have on their machine

* Testing
  * We could really improve here! Right now it's all manual... :-(
  * Single build, with subsequent jobs to test on each os.

* Summary
  * env vars
  * paths
  * home directory
  * shells
