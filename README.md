# flakeOS

**flakeOS** is an independent Linux distribution for desktop use, built from scratch using Arch/Artix tooling. Its main focus is simplicity, stability, and system resilience: if something breaks, flakeOS can automatically roll back to a previous working state.

## Philosophy

- **Simple.** No unnecessary abstractions or layers — just a straightforward system that's easy to understand.
- **Lightweight and fast.** Designed to run even on older and low-end hardware.
- **Resilient.** Automatic snapshots and rollback mechanisms make the system extremely difficult to render unusable.
- **Independent.** Its own package manager, window manager, and repository — without unnecessary dependencies on external infrastructure.

## Current Status

The project is under active development (pre-alpha). The following features are already working:

- 🏗️ Base system running runit + glibc (Artix bootstrap)
- 📦 Custom signed pacman repository `[flakeos]`
- 💽 Boots in QEMU with Btrfs + GRUB
- 🌱 Btrfs snapshots (`@`, `@snapshots`) created before every system update
- ⏪ Automatic rollback to the last known working snapshot after failed boots (using a GRUB boot counter), with a clear on-screen notification
- 🛡️ `flakeos-watchdog` — automatic recovery of individual critical files from the latest snapshot
- In development: custom WM '[flakeWM]'

## Roadmap

- [ ] Protect `/usr` against corruption (read-only and/or watchdog)
- [ ] Manual rollback command
- [ ] Custom package manager (currently based on a pacman/libalpm fork)
- [ ] AUR/Flatpak alternative + source-based package building inspired by Gentoo
- [ ] Custom WM with graphical configuration tools (no config files, "Good Lock for PC"), with the ability to choose a WM during installation
- [ ] Application sandboxing/isolation (similar to iOS/OpenBSD)
- [ ] Move the system to another drive/PC without reinstalling
- [ ] Publish the repository and installation images on GitHub Releases

## Technical Details

| | |
|---|---|
| Kernel | Linux |
| Base System | Artix-like bootstrap |
| libc | glibc |
| Init System | runit |
| Filesystem | Btrfs |
| Package Manager | pacman/libalpm (for now) |
| Bootloader | GRUB |

## Installation

⚠️ flakeOS is not yet ready for production use. Build and QEMU installation instructions will be published here as the first release approaches.

## Community

- Telegram channel: https://t.me/flakeoslinux — development updates, questions, and community discussions
- Issues in this repository — bug reports and feature suggestions

## Contributing

flakeOS is a young project, and contributions of all kinds are welcome: testing in QEMU or on real hardware, bug reports, roadmap ideas, and code contributions.

Before submitting a PR, it's best to discuss your idea in an issue or on Telegram.
