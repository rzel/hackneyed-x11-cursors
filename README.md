![hackneyed-preview](https://raw.githubusercontent.com/Enthymem/hackneyed-x11-cursors/master/preview.png "Spinning hourglass is the new spinning cube")

Overview
--------

Hackneyed is a reactionary X11 cursor theme created for personal use (like all artwork I do -- or most people, for that matter).
Inspired by old Windows 3.x cursors, Hackneyed brings an old school feel to your wobbly-windowed, docky and blocky desktop of today.

Installation
------------
Make sure you have ImageMagick (>=6.8.6), Inkscape (>=0.48.4), GNU make and xcursorgen installed.
Inkscape is _not_ optional; ImageMagick would revert to its own SVG renderer if it wasn't found,
and results would be suboptimal.

`make pack` will drop you a tarball with the full theme, including the left-handed one. If you want either the left-
or the right-handed theme, use the targets `ldist` or `dist`, respectively.

Other useful targets: `all`, `theme` and `theme.left`. These only generate the cursor files without packing them.

If you don't feel like building it from source, grab the tarball from [xfce-look.org]("http://xfce-look.org/content/show.php/Hackneyed?content=165283").

Hackneyed's build system is simply a collection of shell scripts and a Makefile. It wasn't hard to write, and it shouldn't be hard to understand.

License
-------
Hackneyed is released under the MIT/X11 license.

Credits
-------
* do-symlinks.sh, rewrite of addmissing.sh, which was taken from
  dummy-x11-cursors by ultr (on kde-look.org)

* some SVGs taken from openclipart.org (pencil, pirate and coffee_mug as far as I can remember)

Bugs
----
Now that I'm back to GitHub, I have a free bugtracker again;  please report any
bugs you might find, or any enhancements you might want.

A word about hashes
-------------------
libXcursor has an undocumented "hash logger", which is triggered when one exports a variable called
XCURSOR_DISCOVER, no matter the value. The hashes are printed on the terminal, so it's important
that you don't do this from a graphical application launcher. The code is in xlib.c, in a function called
XcursorLogDiscover.

You should not take into account the hashes for masks, i.e., the filled
"images" displayed. Only consider hashes that return some random hex number
(as in "Cursor hash XXXXX returns 0xdeadbeef").

Useful links
------------
* [Freedesktop.org's cursor specification](http://www.freedesktop.org/wiki/Specifications/cursor-spec/ "We aren't a standards organization yadda yadda yadda")

* [CSS cursors](http://dev.w3.org/csswg/css-ui/#propdef-cursor "2drafty4u")

* [Test page for CSS cursors](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor "Firefox is the only browser that uses more than a couple of cursors from the X11 theme")

* [Qt requirements for X11 cursors](http://qt-project.org/doc/qt-4.8/qcursor.html#a-note-for-x11-users)

* [Core X11 cursors](http://tronche.com/gui/x/xlib/appendix/b/ "coffee_mug > all")

* [ComixCursors README](http://www.filewatcher.com/d/Debian/all/x11/comixcursors-lefthanded-opaque_0.7.2-3_all.deb.2350708.html "I blame Google for not finding this sooner")

On XFCE
-------
XFCE (at least on Fedora) doesn't fully load a custom cursor theme at login unless it's set as the "default" theme. If you got pissed off like me
and are looking for a fix, here it is:

```
[Icon Theme]
Inherits=Hackneyed
```

Paste the two lines above into a file called "index.theme", save it on ~/.icons/default and set the mouse theme as "default".
