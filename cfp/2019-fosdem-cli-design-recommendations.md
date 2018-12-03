# Title
Designing Command-Line Tools People Love

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
vibrant inclusive open-source communities around them.

Carolyn is a maintainer for Kubernetes Service Catalog and the GoMods Athens Proxy.
She runs Women Who Go, and organizes for the Chicago chapters of Women Who Go and
Write/Speak/Code.

In between code reviews, Carolyn enjoys hauling her cookies around the world to
share her love of Go, containers, and excessive emoji. 🌈 ✨

# Notes
I've built a few popular OSS command-line tools in Go, such as
Docker Version Manager (dvm), dep, and svcat. Every time I begin a new project,
I have an opportunity to incorporate the most useful designs
from the previous, throw out things that didn't work well, and try new ideas.

Here's what has stuck around:

- Making use of pre-existing libraries or tools like spf13/cobra for structuring the cli,
  and combining it with spf13/viper to handle defaulting flags with environment variables.
- Package structure, such as splitting up domain logic from the cli wiring so
  that people can reuse the cli in their own code.
- Composing commands to make it easier to quickly standardize flags and
  validation across commands. For example making a command composed of other
  structs that handle defining flags, validating and parsing input or handling
  behavior common to multiple commands.
- Passing context with stdout, stdin, stderr, and the filesystem (using spf13/afero)
  to make interacting with boundary systems consistent and testable.
- Testing strategies, such as how to test the cli output without re-testing other
  packages logic, validation, error handling calling external executables or
  services, without creating awkward, fragile tests.
- Common publishing tasks such as a version command, cross compiling, installation
  and upgrading your cli.
- Suggestions for structuring your commands to help users quickly and intuitively
  learn your cli.
