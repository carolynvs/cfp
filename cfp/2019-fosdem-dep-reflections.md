# Title
The Rise and Fall of dep - Reflections on OSS Community Building

# Abstract
The dep package manager wasn't built by a single person or company. It was
created by the Go community, for the Go community. I learned a lot as a maintainer,
not just about building software, but how to collaborate effectively in the Go ecosystem.
I'll share the highs and lows, lessons learned, along with the best practices that evolved
from dep and how they are being applied to other Go projects, such as the Athens Proxy.

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
This is a reflection on what I've learned about open-source software and community
building from being a core maintainer on dep. The talk will NOT touch on the drama
of dep vs. go modules, or how that came about.

If the talk title is too controversial, we could shorten it to simply
"Reflections on OSS Community Building".

Instead I am focusing on how we ran the project, brought on new contributors,
collaborated with the community on design, handled being a maintainer, and
how I am applying what I learned to other Go projects.

Here are some of the points I will touch upon:
- Encouraging contributors
- How our project hierarchy for maintainers and reviews caused bottlenecks and hurt momentum.
- Our engagement with the community on the design of dep, and how that changed
  after our first release.
- How I went from a nobody to a maintainer, and how that shaped how I structure
  the "contributor ladder" for projects that I manage now.
- The concept of code "ownership", and how that can hurt a project.
- PR philosophy, "mega PRs" vs. follow-on PRs, and how that affects merge rates
  and getting repeat contributions.
- Release cadence and its impact on momentum and community trust.
- Managing external project dependencies and risk, for example balancing our desired
  design vs. what would be considered to be merged into the go toolchain. This had
  a large impact on our design and I've changed how I handle project risk for Athens
  based on this experience.

# Outline
