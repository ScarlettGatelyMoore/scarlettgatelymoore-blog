---
title: "KDE snaps, Debian packaging adventures, and what's next"
description: "Updated KDE content snaps with Qt 6.11.1, KF6 6.27.0, and Applications 26.04.3, critical bug fixes, Debian packaging of Rust crates for Plasma 6.7.0, and what's on the horizon."
pubDate: 2026-07-05
tags: ["kde", "snap", "kubuntu", "debian", "linux", "planet-kde"]
heroImage: ""
---

A lot has been happening across KDE snaps and Debian packaging lately. Here's a full rundown of what's been done, what's in progress, and what's coming next.

## Updated KDE content snaps

The KDE content snaps have been updated with:

- **Qt 6.11.1**
- **KF6 6.27.0**
- **KDE Applications 26.04.3**

These underpin all KDE application snaps, so the update flows through to every snap built on top of them.

## Critical bug fixes

Two significant snap issues have been addressed that are worth highlighting.

The first was a serious bug where [some snaps were potentially causing data loss by messing up the home folder](https://forum.snapcraft.io/t/some-snaps-may-mess-up-the-home-folder-and-cause-loss-of-data/51542/8) — a critical issue that needed prompt attention.

The second relates to [Snapcraft 9.0 testing](https://forum.snapcraft.io/t/call-for-testing-snapcraft-9-0/51348/18), during which it was discovered that all runtime environment variables for the `kde-neon-6` extension had somehow been removed. This has been resolved by adding them back to the launcher script.

## What's next: kde-neon-6 core26 support

Work has begun on [kde-neon-6 core26 support](https://github.com/canonical/snapcraft/issues/6297) in Snapcraft — an important step toward modernizing the KDE snap extension stack. This is a complex piece of work and progress will be shared as it develops.

## Debian packaging adventures: Rust crates for Plasma 6.7.0

On the Debian side, there's a fun packaging adventure underway. KDE Plasma 6.7.0 requires a new Rust crate dependency — `cssparser_color` — which has turned into a chain of approximately **20 dependency packages** that all need to be packaged for Debian first.

Rust packaging in Debian has its own set of conventions and complexities, but it's genuinely interesting work. Each crate in the dependency chain needs to be packaged correctly before the next one can be tackled. Progress is being made and this work directly benefits Kubuntu once it lands in Debian.

Once the Rust crate adventure is wrapped up, the next agreed task is finishing up **plasma-login-manager** packaging — which promises to be another adventure entirely.

## Support this work

This is all volunteer work done in my own time alongside a day job. If you find value in KDE snaps, Kubuntu, or Debian packaging work, please consider a small contribution — it genuinely helps keep things moving.

<div style="margin: 2rem 0;">
  <a href="https://www.gofundme.com/manage/help-with-gas-groceries-during-tough-times" style="background: rgb(0, 168, 69); color: rgb(255, 255, 255); text-decoration: none; font-family: Verdana, sans-serif; display: inline-block; font-size: 16px; border-radius: 5px; line-height: 24px; padding: 8px 24px;">Support via GoFundMe</a>
</div>

Any contribution toward gas and groceries during a tough stretch is deeply appreciated and helps ensure this work can continue.

## Get involved

Questions, bugs, or just want to follow along?

- **KDE Snap discussion:** [#snaps:kde.org](https://matrix.to/#/#snaps:kde.org)
- **Kubuntu development:** [#kubuntu-devel:ubuntu.com](https://matrix.to/#/#kubuntu-devel:ubuntu.com)
- **KDE Bug Tracker:** [bugs.kde.org](https://bugs.kde.org)
