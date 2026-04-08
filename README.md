# macOS Persistence Cheatsheet

A practical DFIR-focused cheatsheet for identifying, triaging, and reviewing macOS persistence mechanisms. With additional context such as scope, required privilege, source of truth, signal level, false-positive risk and review guidance.

![light theme](image1.png)

![dark theme](image2.png)

## Features

- Light & dark theme.
- Covers 39 macOS persistence mechanisms across core launch, shell and scheduled execution, extensions and handlers, adjacent and legacy techniques, and profiles / MDM.
- Includes search and interactive legend filters to quickly narrow mechanisms by scope, required privilege, source of truth, signal, and false-positive risk.
- Provides quick navigation, reading/compact density modes, and a focus mode.
- Includes a synchronized mechanism overview to scan all documented techniques at a glance.
- Documents artifact paths, collection and triage notes, execution triggers, and review guidance for each mechanism.

## Official page

- [macOS Persistence Cheatsheet](https://jaybird1291.github.io/blog-cyber/posts/macos-persistence-cheatsheet/)

## Current version

The current published version is `v1.2` dated `2026-04-08`.

Assets currently present in the repository:

- `macos-persistence-cheatsheet-light-v1.2.html`
- `macos-persistence-cheatsheet-dark-v1.2.html`
- `macOS Persistence Cheatsheet Light v1.2.pdf`
- `macOS Persistence Cheatsheet Dark v1.2.pdf`

### v1.2 changelog

**Summary**

- The number of documented mechanisms increased from `31` to `39` with `8` new rows and no removals.

**Changed**

- Improved the overall color palette.

**Added**

- Added a `Privileged Helper Tools` entry covering classic `SMJobBless` layouts and modern bundle-embedded helpers.
- Added an `SSH rc` entry for `~/.ssh/rc` and chained payload drops commonly staged under `~/.security/`.
- Added a `Calendar Alerts / EventKit` entry covering alarm-based execution triggers and related calendar artifacts.
- Added a `Finder Sync Extensions` entry for `.appex` bundles registered through `pluginkit`.
- Added an `Application Support helpers` entry for suspicious executables, scripts, and launch-style `.plist` files under `~/Library/Application Support/`.
- Added an `Application startup scripts` entry for app-specific launch hooks such as Atom, iTerm2, and Sublime Text startup scripts.
- Added an `App preference triggers` entry for persistence hidden in user preferences such as Dock tiles, Terminal command strings, and Screen Saver modules.
- Added a `TCC / Accessibility Grants` entry covering user and system `TCC.db` as a capability-amplification surface adjacent to persistence.
- Added the initial GitHub repository skeleton for publishing and releasing cheatsheet assets.

**Expanded**

- Expanded `Shell init (zsh)` and `Shell init (bash / sh)` to include hidden helper drops under `~/.security/`.
- Expanded `Cron` to include hidden payload paths such as `~/Public/Drop Box/.share.sh`.
- Expanded `Application / daemon plug-ins` to include `Sublime Text` packages, `~/.vim/plugin`, and `~/Library/Application Support/xbar/plugins`.
- Expanded `Login Hooks` to include the root-scoped `com.apple.loginwindow.plist` and shared payload staging under `/Users/Shared/.security/`.
- Expanded `Periodic Jobs` to include `/usr/local/etc/periodic/{daily,weekly,monthly}` in addition to the system `/etc/periodic` tree.
- Expanded `KEXTs` to include `/System/Library/Extensions` alongside `/Library/Extensions`.

## Version history

- `v1.2` (`2026-04-08`): expanded coverage from 31 to 39 mechanisms and refreshed the visual design
- `v1.1` (`2026-04-08`): UI polish, improved scroll behavior, focus mode cleanup, and overview badge fixes
- `v1.0` (`2026-04-07`): initial published version

## Contributing

Contributions are welcome through issues and pull requests.

You can help by reporting inaccuracies, suggesting missing persistence mechanisms, improving triage guidance etc.

Please try to keep contributions:
- practical and technically accurate 
- concise and consistent with the current structure
- synchronized across versioned and published assets when relevant

