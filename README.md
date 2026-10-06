# GATE22

GATE22 is a native macOS terminal and SSH client focused on fast local shell access, saved SSH connections, multi-terminal workflows, and broadcast input.

## Download

Download the latest signed and Apple-notarized DMG from **Releases**:

https://github.com/ClaudiuFlorea/GATE22/releases/latest

Current release: **1.0.1**

GATE22 is distributed directly for macOS and is not distributed through the Mac App Store.

## Highlights

- Real local `zsh` sessions
- Saved SSH connections with configurable folders
- Secure password storage in macOS Keychain
- Read-only `~/.ssh/config` integration with configurable config path
- Single, Columns, Rows, and Grid terminal layouts
- Multi-session selection and Close Selected
- Broadcast Input across selected terminal sessions
- Connection search and keyboard shortcuts
- Light and dark application themes
- Installed monospace font selection and live font sizing
- Native macOS Settings and menu integration
- Apple Developer ID signing and notarization
- Automatic updates with Sparkle 2

## Security

GATE22 does not store SSH passwords in its connection JSON files. Saved SSH passwords are stored in the macOS Keychain and delivered to OpenSSH through a hardened local AskPass flow.

See [SECURITY.md](SECURITY.md) for security reporting and implementation notes.

## Privacy

GATE22 has no GATE22 cloud account or application backend. Local configuration stays on the Mac. Network connections are made for the SSH sessions the user opens and for update checks through Sparkle.

See [PRIVACY.md](PRIVACY.md).

## Updates

GATE22 uses Sparkle 2 for signed application updates.

Update metadata is published in:

https://raw.githubusercontent.com/ClaudiuFlorea/GATE22/main/appcast.xml

The application also provides **Check for Updates…** from the macOS application menu.

## Releases

- **1.0.1** — Sparkle update path validated end-to-end
- **1.0.0** — Initial public release

See [CHANGELOG.md](CHANGELOG.md) for details.

## Source code

GATE22 is closed-source software.

This public repository is used for:

- release downloads
- Sparkle update metadata
- changelog and documentation
- issue tracking

The application source code is not published in this repository.
