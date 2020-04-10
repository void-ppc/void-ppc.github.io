---
layout: std
title: Void Linux for PowerPC/Power ISA - Downloads
---
* TOC
{:toc}

## Download installable base live images

***PLEASE NOTE: If you choose Network as the installation source, a desktop
environment will not be installed regardless of what you are booting!***

It is, however, recommended to use network installation when you can, as only
then you can get latest packages out of the box without having to update the
system.

There are installable live images for all 6 archs. You need to choose the kind
you want, and whether you want a desktop environment out of box or not.

All **live images** and **rootfs tarballs** are available at:

* [https://repo.voidlinux-ppc.org/live/current](https://repo.voidlinux-ppc.org/live/current)

The ppc64le images have these requirements:

- At least a POWER8 CPU or equivalent (POWER ISA 2.07, with little endian
  AltiVec/VSX support; notably e6500 is not supported)
- Currently OpenFirmware (SLOF) and OpenPOWER based systems are tested

The ppc64 images have these requirements:

- At least a PowerPC 970 CPU or equivalent (AltiVec required; so 970/G5, Cell,
  POWER6/7/8/9, e6500 will work, while e5500 and POWER4/POWER5 will not)
- Currently OpenFirmware (SLOF, Apple) and OpenPOWER based systems are tested

The ppc images have these requirements:

- A generic PowerPC CPU
- Currently OpenFirmware based Apple systems are tested

All require at least 350MB disk space for installation. 64-bit systems should
have at least 96MB RAM, 32-bit ones can do with less.

These may not be exhaustive, but the live images contain data necessary for
boot on OF and OpenPOWER systems and utilize GRUB. If you succeed in running
the live ISOs on other systems (or know how to make them work), please let us
know.

Log in as **anon/root**, password **voidlinux**.

To start the installer just execute the *void-installer* utility with enough
permissions (i.e *sudo*). The installer has paths for OpenPOWER, Apple and
CHRP systems.

In addition to the plain command line image, there is also a graphical flavor
with the Xfce desktop environment. Other graphical flavor images are currently
not planned, as it's a lot of effort to make and test them, but you can still
install a desktop of your choice yourself.

It is recommended that you have enough RAM (at least 256 or 512MB) available
when using the graphical images.

## Verifying file integrity

The
[sha256sums.txt](https://repo.voidlinux-ppc.org/live/current/sha256sums.txt)
file contains the `SHA256` hashes to verify the integrity of the downloaded files.

## Mirrors

There are several mirrors to help lighten the load on the primary infrastructure.

Tier 1 mirrors sync directly from the primary and contain everything. They are
also required to provide https. Other mirrors may sync from somewhere else and
are allowed to host specific things only (and may not always be up to date).

To change your mirrors to use a different set, you must create files
in `/etc/xbps.d` with the same names as those in `/usr/share/xbps.d`.
Once you have created such files, replace the URL with one of the servers
below. Only the files containing 'repository' in the filename need to be
duplicated to `/etc/xbps.d/`.

The default is [https://auto.voidlinux-ppc.org](https://auto.voidlinux-ppc.org).
This is supposed to be load-balancing between available Tier 1 mirrors, but that
currently does not work, so it's equivalent to the primary for the time being.

### Tier 1 Mirrors

  * <https://repo.voidlinux-ppc.org> (USA: Chicago)
  * <https://mirrors.servercentral.com/void-ppc> (USA: Chicago)

### Tier 2 Mirrors

  * <http://ftp.lysator.liu.se/pub/void-ppc> (EU: Sweden)
  * <http://lysator7eknrfl47rlyxvgeamrv7ucefgrrlhk7rouv3sna25asetwid.onion/pub/void-ppc> (EU: Sweden)
  * <https://ppc.exqa.de> (EU: Germany)
