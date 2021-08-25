---
title: New ISO images
layout: post
---

Since the April 2020 images were getting stale, there is now a new batch.
There's nothing much to talk about when it comes to functionality, as the
ISOs are just a way to bootstrap a new system and you get all the updates
you need through a rolling release channel, but there are some things
that are noteworthy:

* OpenSSL is now used instead of LibreSSL
* Rootfs tarballs will no longer have broken lib64 symlinks
* A new version of GRUB (2.06)
* Linux 5.13 kernel is default, with 4.4 backup on big endian

The hardware requirements remain the same. Likewise, the same set of images
is shipped as before, i.e. ppc64le, ppc64, ppc, all for glibc and musl,
with console and graphical xfce flavors.
