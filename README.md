# macOS Persistence Cheatsheet

A practical DFIR-focused cheatsheet for identifying, collecting, triaging, and reviewing macOS persistence mechanisms.

The goal is not only to list persistence locations, but to help investigators answer the questions that matter during incident response, forensic analysis, and threat hunting:
- Where does the artifact live?
- What privilege is required to create or modify it?
- Is disk state enough, or is live state required?
- What should be collected first?
- What should be reviewed to separate legitimate administration from suspicious persistence?

![Light theme](image1.png)

![Dark theme](image2.png)

## Official page

- [macOS Persistence Cheatsheet](https://jaybird1291.github.io/blog-cyber/posts/macos-persistence-cheatsheet/)

## Current version

The current published version is `v2.0`, dated `2026-04-26`.

Release notes:

- [v2.0 release notes](https://github.com/jaybird1291/macOS-persistence-cheatsheet/releases/tag/v2.0)

Assets currently present in the repository:

- `macos-persistence-cheatsheet-light-v2.0.html`
- `macos-persistence-cheatsheet-dark-v2.0.html`
- `macOS Persistence Cheatsheet Light v2.0.pdf`
- `macOS Persistence Cheatsheet Dark v2.0.pdf`

## Features

- Light and dark theme.
- Covers `49` macOS persistence and persistence-adjacent mechanisms.
- Organized across:
  - Core Launch & Login Persistence
  - Authentication & Access Persistence
  - Shell & Scheduled Execution
  - Extensions & Handlers
  - Adjacent & Legacy Techniques
  - Profiles & MDM
- Includes search and interactive legend filters.
- Filters mechanisms by:
  - Scope
  - Required privilege
  - Source of Truth
  - Acquisition type
- Uses an acquisition-aware DFIR triage model:
  - `Offline`
  - `Both`
  - `Live preferred`
  - `Offline partial`
- Provides artifact paths, collection commands, inspection commands, triggers, and review guidance for each mechanism.
- Includes quick navigation, reading / compact density modes, and focus mode.
- Includes a synchronized mechanism overview to scan all documented techniques at a glance.
- Includes a generated `Sources & References` bibliography with clickable `[Sx]` references.
- Uses an offline-safe system font stack instead of externally hosted fonts.

## Triage model

Each mechanism is documented using a consistent investigation-oriented structure.

| Field | Purpose |
| --- | --- |
| `Mechanism` | The persistence or persistence-adjacent technique being reviewed. |
| `Required privilege` | The access generally required to create, modify, or abuse the mechanism. |
| `Source of Truth` | Whether disk artifacts, live state, or both are needed for reliable triage. |
| `Collection / Triage` | Paths, commands, and pivots useful during collection and analysis. |
| `Trigger` | The condition that causes execution or activation. |
| `What to review` | Practical review guidance, suspicious conditions, and prioritization notes. |

## Acquisition model

The cheatsheet uses an explicit acquisition model to avoid treating all mechanisms as equally visible from disk.

| Acquisition | Meaning |
| --- | --- |
| `Offline` | Disk artifacts are usually sufficient for meaningful review. |
| `Both` | Disk and live state should both be reviewed. |
| `Live preferred` | Live state is the preferred source of truth. Offline artifacts may be incomplete, misleading, or version-dependent. |
| `Offline partial` | Some useful pivots exist on disk, but live state is required for confidence. |

## v2.0 highlights

`v2.0` is a major public release update from `v1.2.1`.

### Summary

- Expanded the cheatsheet from `39` to `49` mechanisms.
- Added `10` new mechanism rows with no removals.
- Reworked the model from `Signal` / `False Positive Risk` scoring toward acquisition-aware DFIR triage.
- Added a maintainable, JS-generated `Sources & References` bibliography with clickable `[Sx]` references.

### Added mechanisms and coverage

- Dedicated `Authentication & Access Persistence` section.
- `PAM stack / pam.d configuration`.
- `sudoers / sudo policy`.
- `AuthorizationDB rules`.
- `Local accounts / hidden users / Remote Login`.
- `Firefox Extensions`.
- `Input Methods / Input Sources`.
- `Screen Saver bundles`.
- `Folder Actions / Automator / Quick Actions`.
- `Mail.app Rules` with AppleScript actions.
- `Declarative Device Management / Managed background tasks`.

### Expanded guidance

- Expanded SSH persistence triage, including:
  - all users
  - `/var/root`
  - effective `sshd_config`
  - `AuthorizedKeysFile`
  - `AuthorizedKeysCommand`
  - `Include`
  - `Match`
  - Remote Login state
- Expanded browser extension coverage with:
  - Firefox enterprise deployment
  - Firefox policies
  - Firefox native manifest pivots
  - Chromium Native Messaging Host pivots
  - Safari native-app messaging pivots
- Expanded MDM-related coverage around:
  - PPPC / TCC
  - Managed Login Items
  - certificate trust
  - ServiceManagement
  - managed preferences
- Expanded Configuration Profiles triage around:
  - `profiles list`
  - `profiles show`
  - enrollment state
  - parseable XML output
  - payload correlation
- Expanded System Extensions and KEXT guidance.
- Expanded TCC / Accessibility Grants triage with schema-first review notes.
- Expanded BTM / SMAppService guidance around `sfltool dumpbtm`.

## Version history

- `v2.0` (`2026-04-26`): expanded to 49 mechanisms, added acquisition-aware DFIR triage, added Authentication & Access Persistence, added generated references.
- `v1.2.1` (`2026-04-14`): code cleanup.
- `v1.2` (`2026-04-08`): expanded coverage from 31 to 39 mechanisms and refreshed the visual design.
- `v1.1` (`2026-04-08`): UI polish, improved scroll behavior, focus mode cleanup, and overview badge fixes.
- `v1.0` (`2026-04-07`): initial published version.

## Contributing

Contributions are welcome through issues and pull requests.

Useful contributions include:

- reporting inaccuracies
- suggesting missing persistence mechanisms
- improving triage guidance
- adding references
- clarifying version-specific macOS behavior
- improving collection or inspection commands
- improving review logic for noisy enterprise environments

Please try to keep contributions:

- practical and technically accurate
- concise and consistent with the current structure
- focused on DFIR, detection engineering, threat hunting etc.
- synchronized across versioned and published assets when relevant
