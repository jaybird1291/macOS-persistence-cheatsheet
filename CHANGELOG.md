# Changelog

All notable changes to this project will be documented in this file.

This format follows the spirit of Keep a Changelog and Semantic Versioning.

## [1.2.0] - 2026-04-08

### Summary

- The number of documented mechanisms increased from `31` to `39` with `8` new rows and no removals.

### Changed

- Improved the overall color palette.

### Added

- Added a `Privileged Helper Tools` entry covering classic `SMJobBless` layouts and modern bundle-embedded helpers.
- Added an `SSH rc` entry for `~/.ssh/rc` and chained payload drops commonly staged under `~/.security/`.
- Added a `Calendar Alerts / EventKit` entry covering alarm-based execution triggers and related calendar artifacts.
- Added a `Finder Sync Extensions` entry for `.appex` bundles registered through `pluginkit`.
- Added an `Application Support helpers` entry for suspicious executables, scripts, and launch-style `.plist` files under `~/Library/Application Support/`.
- Added an `Application startup scripts` entry for app-specific launch hooks such as Atom, iTerm2, and Sublime Text startup scripts.
- Added an `App preference triggers` entry for persistence hidden in user preferences such as Dock tiles, Terminal command strings, and Screen Saver modules.
- Added a `TCC / Accessibility Grants` entry covering user and system `TCC.db` as a capability-amplification surface adjacent to persistence.
- Added the initial GitHub repository skeleton for publishing and releasing cheatsheet assets.

### Expanded

- Expanded `Shell init (zsh)` and `Shell init (bash / sh)` to include hidden helper drops under `~/.security/`.
- Expanded `Cron` to include hidden payload paths such as `~/Public/Drop Box/.share.sh`.
- Expanded `Application / daemon plug-ins` to include `Sublime Text` packages, `~/.vim/plugin`, and `~/Library/Application Support/xbar/plugins`.
- Expanded `Login Hooks` to include the root-scoped `com.apple.loginwindow.plist` and shared payload staging under `/Users/Shared/.security/`.
- Expanded `Periodic Jobs` to include `/usr/local/etc/periodic/{daily,weekly,monthly}` in addition to the system `/etc/periodic` tree.
- Expanded `KEXTs` to include `/System/Library/Extensions` alongside `/Library/Extensions`.

## [1.1.0] - 2026-04-08

### Changed

- Compacted the view controls to reduce visual footprint.
- Strengthened the glass effect on the sticky controls panel.
- Trimmed several longer UI elements.
- Harmonized several labels.

### Scroll Behavior

- The helper text (`control-copy`) now hides on scroll.
- The `quick-nav` shifts upward to keep the header more compact.
- The scrolled layout is more responsive on intermediate screen widths.

### Focus Mode

- Overview tags are hidden in focus mode for a cleaner reading experience.

### Overview / Mechanism

- Added and fixed badges for `Scope`, `Source of Truth`, `Signal`, `Required Privilege`, and `False Positive Risk`.
- Standardized badge ordering.
- Fixed the `False Positive Risk` badge color.
- Fixed missing color styling for `Required Privilege` and `Source of Truth`.

## [1.0.0] - 2026-04-07

### Added

- Initial public release of the macOS Persistence Cheatsheet.
