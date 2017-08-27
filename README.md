[![logo](https://cdn.rawgit.com/KillWolfVlad/kodi-standalone-improved-AUR/478668358427731959ea6ec57c4c93f22daf9571/logo.svg)](https://kodi.tv/)

# Kodi Standalone Service (_improved_)

A simple `systemd` service to run `kodi` in standalone mode

It is forked from [graysky2/kodi-standalone-service](https://github.com/graysky2/kodi-standalone-service)

We improved kodi user creation and `systemd` service to allow you use 80 port in `kodi` web interface

# Arch Linux and friends

Just download source code and type to build and install package

```bash
makepkg -is
```

then manipulate with `kodi.service`

# Note

Most users should not `/etc/X11/Xwrapper.config` since the created X server becomes the [controlling process](http://www.freedesktop.org/software/systemd/man/systemd.exec.html#StandardInput=) of the VT to which it is bound. Most users does not mean all users. There have been reports of some AMD users still requiring this file. As well, users of Xorg's native modesetting driver may also require it.

The recommendation is to first try starting `kodi.service` without it, but if the service fails to start X, you may need to create `/etc/X11/Xwrapper.config` which should contain the following:

```
needs_root_rights = yes
```

# Credit

Note that this service was provided by the Arch Linux maintainers of the official kodi package, but was removed upon the [1.16-1 release of Xorg](https://git.archlinux.org/svntogit/community.git/commit/trunk?h=packages/xbmc&id=9763c6d32678f3a3f45c195bfae92eee209d504f).
