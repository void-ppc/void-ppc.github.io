---
title: Repositories now complete (and a new primary mirror)
layout: post
---

The binary repositories have now reached completeness, i.e. everything not
explicitly marked so is now built.

That doesn't mean we ship every single piece of potentially buildable software
(notably Texlive is still missing and will need refactoring the templates to
build it from source), but generally it's in a similar state to other
distributions and sometimes better (e.g. we ship qt5-webengine at least
on some targets).

For current statistics, always refer to the Packages link in the menu.

Current TODO items include spinning a new set of ISO images (but before that,
fix known installer issues, enable serial console access in live and some
other things) and extending the documentation and FAQ.

Also, I've been granted commit access in upstream Void in December. That means
the flow of upstream changes is now a lot quicker and smoother, and allows me
to keep the repos in sync as much as possible. While it is not possible to
mainline the whole project at this point other than source code (unfortunately
Void right now cannot take in any more builders, native or cross, and I would
ideally like to keep the builds native), having the source upstreamed is a big
help and void-ppc will provide staging and binary repos indefinitely.

Speaking of that, our community member `zdykstra` has recently donated a new
primary hosting mirror, which means we now have a much greater storage space
as well as much faster network connectivity. The server is hosted in Chicago,
IL. There's also a number of other mirrors to choose from.
