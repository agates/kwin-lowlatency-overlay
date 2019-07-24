# kwin-lowlatency-overlay

this repository provides gentoo ebuilds for the [kwin-lowlatency](https://github.com/tildearrow/kwin-lowlatency) project.

pull requests are welcome and encouraged.  i merely created this for my own convenience.

# using this overlay

## with repos.conf

[/etc/portage/repos.conf](https://wiki.gentoo.org/wiki//etc/portage/repos.conf) can be used.
to enable this overlay make sure you are using a recent Portage version (at least `2.2.14`), and create a `/etc/portage/repos.conf/kwin-lowlatency-overlay.conf` file containing precisely (the location can be anywhere you want):

```
[kwin-lowlatency-overlay]
location = /usr/local/portage/kwin-lowlatency-overlay
sync-type = git
sync-uri = https://github.com/agates/kwin-lowlatency-overlay.git
priority=9999
```

afterwards, simply run `emerge --sync`.

# installation

## USE Flag

set the `lowlatency` USE flag on the package, e.g. in `/etc/portage/package.use/kwin-lowlatency`:

```
kde-plasma/kwin lowlatency
```

without this flag, the package is identical to the original `kde-plasma/kwin` package.

## install/update the package

update the package with the new use flag:

	sudo emerge -av1 --changed-use kwin
