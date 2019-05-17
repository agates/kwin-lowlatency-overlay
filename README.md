# kwin-lowlatency-overlay

This repository provides gentoo ebuilds for the [kwin-lowlatency](https://github.com/tildearrow/kwin-lowlatency) project.

# How to use this overlay

## with local overlays

[Local overlays](https://wiki.gentoo.org/wiki/Overlay/Local_overlay) should be managed via `/etc/portage/repos.conf/`.
To enable this overlay make sure you are using a recent Portage version (at least `2.2.14`), and create a `/etc/portage/repos.conf/kwin-lowlatency-overlay.conf` file containing precisely:

```
[kwin-lowlatency-overlay]
location = /usr/local/portage/kwin-lowlatency-overlay
sync-type = git
sync-uri = https://github.com/agates/kwin-lowlatency-overlay.git
priority=9999
```

Afterwards, simply run `emerge --sync`, and Portage should seamlessly make all our ebuilds available.

# Installation

## USE Flag

Set the `lowlatency` USE flag on the package, e.g. in `/etc/portage/package.use/kwin-lowlatency`:

```
kde-plasma/kwin lowlatency
```

Without this flag, the package is identical to the original `kde-plasma/kwin` package.

## Install/update the package

Update the package with the new use flag:

	sudo emerge -av1 --changed-use kwin
