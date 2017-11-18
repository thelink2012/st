# thelink2012 st fork

st is a simple terminal emulator for X which sucks less.

This is a fork of [st][st] with a few changes and patches applied for my own needs.

An `PKGBUILD` for Arch is provided, so you may ignore the installation instructions below.

Changes
-----------

The following is a list of changes in this fork:
 
 - Loading settings from Xresources (from [dcat][st-xres] and [neeasade][xst]).
 - Live-reloading of settings on USR1 signal (from [neeasade][xst]).
 - Scrollback patch, including *Shift+MouseWheel* (from [/patches/scrollback](https://st.suckless.org/patches/scrollback/)).

Requirements
------------
In order to build st you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install


Running st
----------
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

Credits
-------
Based on Aurélien APTEL (aurelien dot aptel at gmail dot com) bt source code.

[st]: https://st.suckless.org/
[st-xres]: https://github.com/dcat/st-xresources
[xst]: https://github.com/neeasade/xst

