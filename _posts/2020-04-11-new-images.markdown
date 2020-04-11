---
title: New ISO images
layout: post
---

The old batch was starting to show its age, so there are now some fresh ISO
images. There are also some significant improvements in them. They are marked
20200411.

Let's see:

## Serial console support

There is now support for serial console integrated in the images, so you don't
necessarily need a monitor and/or go through a bunch of hoops to manually set
up the serial console. All you need to do is append some things on the kernel
command line.

For example, on a Talos 2/Blackbird/`qemu-system-ppc64`:

```
console=tty0 console=hvc0
```

The first will get you a monitor as usual, the second the serial console.
Keep in mind that it has to be last! There is a special hook in the live
initramfs that sets up the respective `agetty` services.

## Dual kernels for big endian

Since some Macs have trouble booting on recent 5.x kernels, we're now shipping
a 4.4 LTS kernel as an alternative to the primary (currently 5.4) one. You
can choose between them in the bootloader. So if you have one of those
affected machines, you can at least get the installer booted.

Keep in mind that with a network installation you'll get the default kernel
again. The installer gives you an option to drop into the installed system
before rebooting. You can install a kernel of your choice there.

## Bootstrap partition validation in installer

Since a bunch of people complained about the installer booting fine but the
final system not being bootable and the issue turned out to be swapped
parameter order when creating the bootstrap partition on their Mac (and
therefore the partition having an incorrect type), the installer now checks
whether the partition is correct and tells you ahead if it's not.

## Yaboot shipped in the ISOs

If you're one of those really unlucky people who can't get GRUB to load and
there is no workaround (such one of those described in the FAQ), you can now
use `yaboot` to boot the image. The default is obviously GRUB, but you can
bring it up manually, e.g.:

```
boot ud:,\boot\yaboot conf=ud:,\etc\yaboot.conf
```

Of course, that doesn't mean `yaboot` is supported in the installer; it's still
old and obsolete, and doesn't play nice with the rest of the system (and thus
requires manual maintenance). However, it allows you to get the ISO booted,
install the system without having it set up the bootloader, and set it up
afterwards by hand.

## Fewer graphical flavor images

Since generating all those graphical flavor images took way too long, needed
a ton of space, and some of them didn't even work for various reasons, we are
no longer shipping graphical flavors with the exception of Xfce. Keep in mind
that this **only** applies to the live images! You can still install the
desktop environment of your choice in the final system, of course.

## Other minor stuff

The graphical flavor iamges for 32-bit PowerPC now ship Xorg drivers for
Rage 128 (`r128`) and Rage Pro (`mach64`). This could help some G3s and
so on, but do keep in mind that it won't likely start up out of box, as the
drivers always needed manual configuration (Xorg modelines, etc.)

There have also been assorted fixes in the installer, such as simpler and
more robust code that takes care of setting up the NVRAM stuff to make Void
boot as the default OS. And obviously, the software stack is fresh and updated.

That's it for now. Grab a copy from the Download page, and test it if you have
the hardware. Any issues go into the bug tracker as always, and we have an IRC
channel as well (`#voidlinux-ppc` on Freenode).

Next batch will come once enough crucial fixes have accumulated, or once it
starts getting dated again.
