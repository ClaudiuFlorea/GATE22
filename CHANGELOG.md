# Changelog

All notable public GATE22 releases are documented here.

## 1.0.2

Release hardening and SSH workflow improvements.

### Changed

- Refined the native macOS interface and terminal workspace
- Added saved SSH authentication modes: Password, Identity File, and None
- Added optional SSH Keep Alive
- Improved saved connection and folder management
- Improved Keychain-backed password handling and concurrent SSH authentication
- Added real session information and terminal status metadata
- Added keyboard shortcuts for tabs, layout, broadcast, sidebar, and search
- Enforced a single main workspace window while preserving sessions when reopening it
- Improved persistence recovery and general stability

## 1.0.1

Update infrastructure release.

### Changed

- Added Sparkle 2 application update support
- Added native **Check for Updates…** integration
- Added signed EdDSA update feed support
- Validated the complete update flow from GATE22 1.0.0 to 1.0.1

## 1.0.0

Initial public release.

### Features

- Native macOS terminal with real local `zsh` sessions
- Saved SSH connections and configurable folders
- Secure saved SSH passwords using macOS Keychain
- Read-only `~/.ssh/config` integration with configurable config path
- Search across saved and SSH-config connections
- Single, Columns, Rows, and Grid terminal layouts
- Multi-session selection and Close Selected
- Broadcast Input across selected sessions
- Automatic terminal focus and native macOS keyboard shortcuts
- Light and dark application themes
- Installed monospace font selection and live font sizing
- Native macOS Settings
- Developer ID signed and Apple-notarized direct distribution
