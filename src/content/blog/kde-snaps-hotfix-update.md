---
title: "KDE snaps hotfix release and what's keeping me busy"
description: "A hotfix release of kf6-core24 to work around a Snapcraft 9 bug that was breaking Qt-based snaps, plus an update on current Debian packaging and snap development work."
pubDate: 2026-07-19
tags: ["kde", "snap", "kubuntu", "debian", "linux", "planet-kde"]
heroImage: ""
---

A quick but important update — a hotfix release of **kf6-core24** has been pushed to address a serious upstream bug in Snapcraft 9 that was leaving Qt-based snaps entirely broken for some users.

## The bug

Snapcraft 9 incorrectly sets `LD_LIBRARY_PATH` and `QT_LIBRARY_PATH` in the desktop extensions. A fix had previously landed on the `hotfix/8.14` branch but was only partially applied when merged back to main — meaning Snapcraft 9.0 never received it. The upstream issue is tracked at [canonical/snapcraft#6327](https://github.com/canonical/snapcraft/issues/6327) and remains open at time of writing.

Rather than wait for an upstream fix that hasn't arrived yet, a workaround has been implemented directly in the kf6-core24 content snap launcher script. This restores correct behaviour for Qt-based KDE snaps in the meantime.

If you were experiencing broken KDE snaps, a refresh should resolve it:

```bash
sudo snap refresh
```

## What else is happening

While the hotfix was the most urgent item, there is plenty of other work in progress.

**Debian packaging — Rust crates for Plasma 6.7.0**

Good progress here — `cssparser-color` is now packaged for Debian. The current focus is working through the reverse dependencies of `cssparser` to ensure the update doesn't break anything downstream before it lands. This careful dependency validation is exactly the kind of unglamorous but essential work that keeps Debian stable, and in turn keeps Kubuntu stable.

**plasma-login-manager**

Once the Rust crate chain is complete, the agreed next task is finishing up **plasma-login-manager** packaging — another interesting piece of work on the horizon.

**kde-neon-6 core26 support**

Work continues on [core26 support for the kde-neon-6 Snapcraft extension](https://github.com/canonical/snapcraft/issues/6297) — an important step toward modernizing the KDE snap stack.

## A personal note

All of this is volunteer work done alongside a day job. If you find value in KDE snaps being maintained, Kubuntu working well, or Debian getting the packages it needs — any support is genuinely appreciated and helps keep things moving.

<div style="margin: 2rem 0;">
  <a href="https://www.gofundme.com/manage/help-with-gas-groceries-during-tough-times" style="background: rgb(0, 168, 69); color: rgb(255, 255, 255); text-decoration: none; font-family: Verdana, sans-serif; display: inline-block; font-size: 16px; border-radius: 5px; line-height: 24px; padding: 8px 24px;">Support via GoFundMe</a>
</div>

Thank you to everyone who has already contributed — it means more than I can say.

## Get involved

- **KDE Snap discussion:** [#snaps:kde.org](https://matrix.to/#/#snaps:kde.org)
- **Kubuntu development:** [#kubuntu-devel:ubuntu.com](https://matrix.to/#/#kubuntu-devel:ubuntu.com)
- **KDE Bug Tracker:** [bugs.kde.org](https://bugs.kde.org)
