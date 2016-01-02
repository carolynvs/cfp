# Title (60 chars)

Welcoming Windows to the neighborhood: Writing cross-platform first applications

# Abstract (600 chars)

You may not realize it but there are a lot of Windows developers moving into your neighborhood. They are using, and contributing to, open source projects, even those that aren't just for Windows. But here's the rub: many tools are still written "Unix first", shoehorning in support later and this is costing them users.

Lucky for us, Go has strong support for cross-platform development which we can use to welcome our Windows neighbors by writing cross-platform first. Learn some of the Windows quirks that you should take into account, and the Go goodies that will help you conquer them.

# Speaker bio (500 chars)
Carolyn is a software developer from Chicago, though one day she hopes
to escape to the Pacific Northwest in search of faster internet, free-range kittens
and respite from snow blowers. She loves all things automation, developer tools
and anything that will make her fellow developers lives easier; so she's found a good home
at Rackspace on the Developer Experience team. Like a grafted bonsai,
her roots come from many places: happily developing C# applications on a Mac and deploying to Linux.

# Details

## Theme
Developers who only work with Mac OS X and Linux may not be aware that
they have a big, untapped user base. Windows developers used to work in
isolation, but not anymore thanks to the popularity of git, node and Docker.
Not only is Microsoft embracing open source, but enterprises are finally allowing
their developers to use open source libraries and tools. This is an opportunity,
especially for open source projects, but some struggle with how to get started,
as they aren't Windows users themselves.

## Takeaways
* Want to grow your project? Start welcoming these new Windows users.
* Learn about Go's features to write cross-platform first.
* Make it easy for Windows developers to contribute to your project, and
  they can help ease the load of supporting multiple platforms.

## Prerequisite knowledge for this presentation
None!

## Agenda (50 minutes)

* Speaker and Topic Introduction - 5 minutes
* How this all started: Cross-platform tools at Rackspace - 5 minutes
* Rewriting the [Docker Version Manager in Go][dvm] - 10 minutes
* Adding Windows Support to [Carina CLI][carina-cli] - 5 minutes
* Cross-platform Build Tips - 5 minutes
* Cross-platform Testing Tips - 5 minutes
* Summary / Cheat Sheet - 5 minutes

[dvm]: https://github.com/getcarina/dvm
[carina-cli]: https://github.com/getcarina/carina

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
