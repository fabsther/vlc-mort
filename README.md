# VLC media player (Mort)

**[WARNING]** This is a fork of [VLC media player](http://www.videolan.org/vlc/index.html) [2.0 maintenance branch](http://git.videolan.org/?p=vlc/vlc-2.0.git;a=summary) used by myself. Some annoying / useless features are removed (just for myself).

Like *The Luggage* (VLC 1.1), *Twoflower* (VLC 2.0), *Rincewind* (VLC 2.1) and *Weatherwax* (VLC 2.2), *Mort* is also a fictional character in the *Discworld* novel (https://en.wikipedia.org/wiki/Mort).

## Roadmap

(There is definitely no guarantee that any of them will be eventually implemented)

* A GUI for FFmpeg (so you can transcode multimedia files via VLC)
* More Lua scripts in [share/lua/playlist](https://github.com/soimort/vlc-mort/tree/master/share/lua/playlist); maybe integration with [you-get](https://github.com/soimort/you-get)?
* A Lua console
* Danmaku support
* Default to a minimal, dark skin
* Remove the weird traffic cone from VLC (the most ridiculous logo for a media player I've ever seen)

## Requirement

Not a full list of dependencies; only the ones with specific version requirement (which will lead to build failure if wrong versions are used).

* Qt (>= 4, < 5)
* Lua (>= 5.1, < 5.2)
* FFmpeg (libavcodec version < 55)
* VA-API (libva >= 1.2)

## Build

Here's how I build VLC on my system:

```
$ ./bootstrap
$ ./configure --prefix=/usr \
              --sysconfdir=/etc \
              --disable-rpath \
              --disable-visual \
              --disable-projectm \
              --enable-oss \
              --enable-faad \
              --enable-nls \
              --enable-lirc \
              --enable-pvr \
              --enable-ncurses \
              --enable-realrtsp \
              --enable-xosd \
              --enable-aa \
              --enable-vcdx \
              --enable-upnp \
              --enable-opus \
              --enable-sftp \
              LUAC=luac5.1 \
              RCC=/usr/bin/rcc
$ make
$ _ make install
```
