---
title: "KDE Applications snaps are back — stable release"
description: "100+ KDE Application snaps updated and released to stable, with Qt6, KF6, arm64 support, and KDE CI integration. Coinciding with KDE Gear release day."
pubDate: 2026-04-16
tags: ["kde", "snap", "linux", "kubuntu", "planet-kde"]
heroImage: ""
---

After a brief hiatus, I'm happy to announce that **100+ KDE Application snaps are back and released to stable**, coinciding with the KDE Gear release today.

These snaps have been rebuilt with updated Qt6 and KF6 content snaps and are available now in the stable channel.

## What's new

**Updated Qt6 and KF6 content snap** — the underlying runtime has been refreshed, so all applications benefit from the latest framework updates.

**arm64 is back** — one of the things I'm most pleased about this cycle is the return of arm64 snap builds. KDE on arm64 hardware is a first-class citizen again.

**KDE CI integration** — snaps are now on KDE's CI infrastructure, giving us much better visibility into build health and regressions going forward. CI-based deployment is still a work in progress, but the foundation is in place.

## Highlights

A few notable releases worth calling out:

**digiKam 8.8.0** — the powerful photo management suite is now in stable:

```bash
sudo snap install digikam
```

**Haruna 1.7.1** — the KDE media player lands at version 1.7.1:

```bash
sudo snap install haruna
```

**KPhotoAlbum 6.2.0** — the KDE photo album and viewer:

```bash
sudo snap install kphotoalbum
```

For any other KDE application snap, simply install from stable:

```bash
sudo snap install <snap_name>
```

Or if you already have a snap installed and want to update:

```bash
sudo snap refresh <snap_name>
```

The updated Qt6 and KF6 content snap will be pulled in automatically as a dependency.

## Found a bug?

If something isn't working as expected, please file it against the relevant snap on the [KDE Bug Tracker](https://bugs.kde.org) or come find us on Matrix:

- **KDE Snap discussion:** [#snaps:kde.org](https://matrix.to/#/#snaps:kde.org)
- **Kubuntu development:** [#kubuntu-devel:ubuntu.com](https://matrix.to/#/#kubuntu-devel:ubuntu.com)

Thank you to everyone who tested during the beta cycle — your feedback made this release better.
