# Changelog

All notable changes to this project will be documented in this file.

## [2.0] - 2026-04-26

### Summary

- Major public release update from `v1.2.1 (14/04/2026)` to `v2.0 (26/04/2026)`.
- Expanded the cheatsheet from `39` to `49` mechanisms with `10` new mechanism rows and no removals.
- Reworked the model from Signal / False Positive Risk scoring toward acquisition-aware DFIR triage.
- Added a maintainable, JS-generated `Sources & References` bibliography with clickable `[Sx]` references.

### Added

- Added a dedicated `Authentication & Access Persistence` section and moved `SSH authorized_keys` and `SSH rc` into it.
- Added `PAM stack / pam.d configuration`.
- Added `sudoers / sudo policy`.
- Added `AuthorizationDB rules`.
- Added `Local accounts / hidden users / Remote Login`.
- Added `Firefox Extensions`.
- Added `Input Methods / Input Sources`.
- Added `Screen Saver bundles`.
- Added `Folder Actions / Automator / Quick Actions`.
- Added `Mail.app Rules (AppleScript actions)`.
- Added `Declarative Device Management / Managed background tasks`.
- Added an explicit `Acquisition` triage dimension with `Offline`, `Both`, `Live preferred`, and `Offline partial` badges, filters, and overview chips.
- Added a top-of-sheet note clarifying that modern `/System/Library/...` paths are mostly protected baseline/reference locations under SSV/SIP.
- Added an extensibility disclaimer to the Extensions section for broader plug-in, script, native messaging, helper app, URL handler, automation, and scriptable-interface surfaces.

### Changed

- Removed the `Signal` table column, legend card, filter group, badges, overview chips, and related JS/CSS.
- Removed `False Positive Risk` / `FP risk` legend, filters, badges, visible metadata, and related JS/CSS.
- Kept the table at six columns: `Mechanism`, `Required privilege`, `Source of Truth`, `Collection / Triage`, `Trigger`, and `What to review`.
- Renamed `Shell, Access, and Scheduled Execution` to `Shell & Scheduled Execution` after moving SSH access persistence into the new Authentication section.
- Added `Sources` to the quick navigation and included the bibliography in quick-nav observation.
- Converted static reference labels into clickable bibliography links with stable IDs, native tooltips, keyboard focus styling, and generated source cards.
- Reordered and renumbered references by document section and row order, ending with the MDM range `S42-S48a`.
- Switched to a standalone/offline-safe system font stack instead of relying on Google-hosted fonts.
- Adjusted legend layout so the four remaining legend cards fit cleanly on a 1080p display.

### Expanded

- Expanded `SSH authorized_keys` coverage to enumerate all users, `/var/root`, effective `sshd_config`, `AuthorizedKeysFile`, `AuthorizedKeysCommand`, `Include`, `Match`, and Remote Login state.
- Expanded browser extension coverage with Firefox enterprise deployment, Firefox policy, Firefox native manifest pivots, Chromium Native Messaging Host pivots, and Safari native-app messaging pivots.
- Expanded `High-impact MDM payloads` with more precise PPPC/TCC, Managed Login Items, certificate trust, ServiceManagement, and managed-preferences language.
- Expanded `Configuration Profiles` triage around modern `profiles list`, `profiles show`, enrollment state, parseable XML output, and payload correlation.
- Expanded `System Extensions` with offline partial pivots while keeping live `systemextensionsctl list` as the preferred activation-state source.
- Expanded `KEXTs` with `kmutil showloaded`, disk bundle enumeration, Apple silicon Reduced Security / approval context, and DriverKit/System Extension nuance.
- Expanded `TCC / Accessibility Grants` with schema-first triage for Mojave/Catalina versus Big Sur+ databases, including `policy_id` for PPPC-managed grants.
- Expanded `BTM / SMAppService` guidance around `sudo sfltool dumpbtm` and the limitations of treating `BackgroundItems-v*.btm` stores as simple plists.
- Expanded checklist and telemetry panels with authentication/access persistence, Firefox/browser automation context, DDM-managed background tasks, and additional log pivots.

### Fixed

- Corrected PPPC wording so Camera, Microphone, Screen Recording, and service-specific privacy classes are not described as universally silently grantable.
- Corrected `com.apple.servicemanagement` wording to describe managed or auto-approved login/background item rules rather than profile-only registration.
- Corrected certificate payload wording so enterprise trust-store manipulation is not overstated as defeating correctly implemented certificate or public-key pinning.
- Corrected `DYLD_* injection / LSEnvironment` wording around SIP, Hardened Runtime, code signing, library validation, and the distinct runtime exceptions involved.
- Corrected `Privileged Helper Tools` SMAppService bundle paths from `LaunchServices` to `Contents/Library/LaunchDaemons` and `Contents/Library/LaunchAgents`.
- Corrected Sublime Text startup-script coverage to use user package locations instead of the signed `Contents/MacOS` app directory.
- Corrected Login Hooks deprecation wording to avoid a contradictory `10.11` claim.
- Added modern `launchctl` syntax context for `At / atrun` while preserving the legacy `load -w` note.
- Added offline backing-file hints for `launchd overrides / disabled state`.
- Added Apple silicon KEXT approval context and stronger review criteria for loaded or approved non-Apple KEXTs.
- Added PAM baseline hashing guidance for `/etc/pam.d/*` instead of relying only on `codesign` checks of SIP-protected modules.
- Updated Input Methods baseline guidance to compare against Apple-shipped input methods on the target OS rather than outdated examples.
- Split Screen Saver coverage out of `App preference triggers` into a dedicated mechanism row.

## [1.2.1] - 2026-04-14

### Summary

- Code cleanup.

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
