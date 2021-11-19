---
title: The future of big endian in Void-PPC
layout: post
---

As the maintenance has been taking a significant toll on my free time
and infrastructure, I can no longer maintain the repositories as they
are. I do not actively use the big endian ports and community participation
in the last few years has not been strong enough to offset that.

That is why starting next year, the `musl` repositories for big endian
(i.e. the `ppc64-musl` and `ppc-musl`) will be dropped.

The `glibc` versions will be retained for the time being, with the
tentative date for their phasing out being January 2023.

In the meantime, if there is interest, the ports will be looking for a
new maintainer. The new maintainer will have to provide the package
builds/repos as well as fix issues that come up. I will still be here
to coordinate upstreaming of patches if needed.

In case no maintainer is found, the repositories will be shut down
without a replacement.

The little endian (`ppc64le` and `ppc64le-musl`) ports are not affected
by this in any way. The experimental `ppcle` and `ppcle-musl` packages
will likewise stay as they are minimal effort.
