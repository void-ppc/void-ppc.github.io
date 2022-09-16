---
title: Project status update for 2023
layout: post
---

Last year I wrote about the plans for phasing out of big endian support
in the project by the end of 2022. This is now being changed. Instead,
I will cease maintenance of the project as a whole beginning January
2023.

That means if the project is to continue, somebody else will have to take
over. They will need to provide their own build infrastructure as well
as everything else, as the public repository hosting will be shutting
down as well.

The main reason for dropping of the project is that I have been working
on a new distro, [Chimera Linux](https://chimera-linux.org). The new
project is fully supported on the POWER architecture (and others) and
is currently in heavy development (but expected to stabilize during 2022).
Users are encouraged to migrate to it once that happens.

I have been thinking about this a lot and came to the conclusion that
there is no reason to keep up maintenance of both projects. Chimera is
explicitly designed to address various shortcomings of Void while
retaining most, if not all of Void's good aspects. That means Chimera
should make for a good successor of the project.

Additionally, big endian support may be coming back in Chimera, at very
least for 64-bit POWER. The viability of 32-bit PowerPC support will be
evaluated as well. However, this will only happen after the project has
stabilized its tier 1 architectures (`ppc64le`, `x86_64` and `aarch64`).
We will be introducing RISC-V 64-bit support as well for those interested.

In the end, the only loss is support for the `glibc` C library, as Chimera
is a musl-only distribution. However, since musl is first-class in the
project, the overall level of polish should be a lot better than in
Void, and for most users there should be no need for concern, especially
on the POWER architecture where there are no proprietary NVIDIA drivers
and other things that would be of concern. Containers, flatpak and other
solutions should prove effective enough in addressing glibc application
compatibility.

If you are interested, feel free to stop by in any of our main channels.
There are links on the Chimera website. I will probably not update this
page any more, but will keep it running for the foreseeable future (the
repositories will shut down next year, however).
