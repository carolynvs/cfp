# Title
Design Command-Line Tools People Love

# Abstract
It is a joy to build command-line tools that are not only easy to learn,
but that other developers are willing to maintain. Often a team's
engineering efforts are spent on the backend, while the cli doesn't receive the same
level of attention. This can result in hard-to-test tools, and dumping maintenance
of them to whoever most recently joined the team.

Learn how to take full advantage of popular Go libraries, structure your Go code
to improve reuse and testability, publish binaries, and of course design your
commands to be user friendly.

# Bio
Carolyn is a software developer based in the wilds of suburban Chicago, working
remote on the Microsoft Azure team. Her passion is developer tools, and building
vibrant inclusive communities around them. In between code reviews, Carolyn enjoys hauling her cookies around the world to
share her love of open-source, containers, and excessive emoji. 🌈 ✨

# Notes
I've built a few popular OSS command-line tools in Go, such as
Docker Version Manager (dvm), dep, and Kubernetes Service Catalog CLI (svcat).
There are a number more that didn't live as long that have
given me a playground to experiment. Each time I begin a new project, I have an
opportunity to incorporate the most useful designs from the previous, throw out
things that didn't work well, and try new ideas.

Here's what has stuck around:

- Suggestions for structuring your commands to help users quickly and intuitively
  learn your cli. Your goal is a predictable cli (not just for native english speakers):
  * Select a grammar, a basis for making decisions about what your commands and
  flags will look like so you aren't arguing later, before you start implementing.
  * Understand existing tools in your ecosystem so you can take advantage of
  muscle memory and point to precedent when desirable.
  * Domain trumps grammar sometimes. Explain when to break with consistency.
  * Have a plan for how people will learn from and use your help text.
- Encourage task oriented commands:
  * Don't just wrap an api
  * Don't stop at code generation
  * Show examples of composite commands that perform useful tasks to demonstrate
  how that is user friendly and wins hearts, e.g. a command that handles making
  a key pair for you then using it elsewhere, instead of assuming you are up for
  googling how to use openssl and combining that manually with this cli.
- Making use of pre-existing libraries to handle common tasks and make it easier
  for people who are used to working on other CLIs to pick up this one easily.
  * spf13/cobra for the flags and commands.
  * spf13/viper for supporting multiple config file formats (heads off arguments
    about yaml vs json vs hcl).
  * spf13/afero for abstracting access to the file system. This helps greatly
  with unit tests.
- Package structure, such as splitting up domain logic from the cli wiring so
  that people can reuse the cli in their own code:
  * Isolate use of cli libraries in `cmd/mycli`.
  * Write a full library for your cli, just like any other application, in a
  separate package, such as `mycli` or `pkg/mycli`.
- Compose commands to make it easier to quickly standardize flags and
  validation across commands. Making a command composed of other
  structs that handle defining flags, validating and parsing input or handling
  behavior common to multiple commands. Many svcat commands have similar
  flags, parsing and validation for outputing to json|yaml|table, and I will show
  we broke that up so it's quick and easy for people to do that for new commands
  without a learning curve.
- Passing "context" (not the stdlib context) such as stdout, stdin, stderr, and
  the filesystem (using spf13/afero) to make interacting with boundary systems
  consistent and testable. This is an area that often gets sloppy in a CLI, and
  makes them hard to test.
- Testing strategies, such as how to test the cli output without re-testing other
  packages logic, validation, error handling calling external executables or
  services, without creating awkward, fragile tests.
- Common publishing tasks such as a version command, cross compiling and publishing
  the resulting binaries, installation and upgrading your cli. (I can drop this
  based on time constraints. I dropped it when I did the talk at FOSDEM and then
  a number of people said they wanted advice on this topic. It's not focused on
  how to cross compile but how to quickly setup publishing a set of binaries with
  and install script and a reliable way to upgrade later, or publish with homebrew, etc).
