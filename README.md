# GATE22

GATE22 is a native macOS terminal and SSH client built for fast local shell access, saved SSH connections, multi-terminal workflows, and broadcast input.

## Download

Download the latest signed and Apple-notarized DMG from **Releases**:

https://github.com/ClaudiuFlorea/GATE22/releases/latest

Current release: **1.0.1**

GATE22 is distributed directly for macOS and is not distributed through the Mac App Store.

## What GATE22 does

### Local terminal

- Opens real local `zsh` sessions through a PTY
- Uses the user's normal shell configuration
- Supports standard terminal behavior such as autocomplete, ANSI colors, copy/paste, scrolling, Ctrl commands, arrow keys, Tab, and interactive tools
- New local shells open as independent sessions

### SSH connections

- Save SSH connections with:
  - name
  - host
  - port
  - username
  - optional identity file
  - optional saved password
- Opens SSH using the system `/usr/bin/ssh`
- Supports normal OpenSSH behavior including:
  - `~/.ssh/config`
  - `known_hosts`
  - SSH agent
  - keys
  - ProxyJump / ProxyCommand
  - custom SSH options handled by OpenSSH
- Saved SSH passwords are stored securely in the macOS Keychain
- SSH connection state is reflected in the sidebar status indicator

### SSH config integration

- Reads SSH aliases from the configured SSH config file
- Default config path: `~/.ssh/config`
- SSH config entries are read-only in GATE22
- A config entry can be copied into a GATE22 folder and then managed as a normal saved connection
- SSH config visibility can be disabled in Settings
- Custom SSH config paths are supported

### Connection organization

- Create, rename, and delete folders
- Move saved connections between folders
- Drag-and-drop support
- Search saved connections and SSH config aliases
- Search matches:
  - connection name
  - host / IP
  - username
  - folder
  - SSH config alias
- Folders start collapsed on app launch

### Terminal view modes

GATE22 can show open sessions in four layouts:

- **Single** — one terminal at a time
- **Columns** — all open terminals side-by-side
- **Rows** — all open terminals stacked vertically
- **Grid** — automatically balanced terminal grid

Tabs always represent real terminal sessions. Switching view mode changes only the layout; sessions are not restarted.

### Multi-session selection

In Columns, Rows, and Grid views:

- select individual terminal sessions
- select all / deselect all
- close selected sessions together
- selected sessions remain clearly highlighted

### Broadcast Input

Broadcast Input mirrors terminal input to selected sessions.

Useful for running the same command on multiple machines at once.

It forwards terminal input at the raw input level, including:

- normal text
- Enter
- Backspace
- Tab
- Ctrl commands
- arrows
- Escape
- supported Option / Meta sequences

Selected broadcast sessions are visually highlighted and the action bar shows when Broadcast Input is active.

Use Broadcast Input carefully: commands are sent to every selected target.

### Appearance

- Light and dark application themes
- Installed monospaced font selection
- Live terminal font size changes
- Terminal appearance updates without restarting active sessions
- Native macOS Settings window

### Updates

GATE22 uses Sparkle 2 for signed application updates.

You can check manually using:

**GATE22 → Check for Updates…**

Sparkle update metadata is published at:

https://raw.githubusercontent.com/ClaudiuFlorea/GATE22/main/appcast.xml

## Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| **⌘T** | New Local Shell |
| **⌘W** | Close current tab / session |
| **⌘K** | Focus Connection Search |
| **⌘⇧S** | Toggle Sidebar |
| **⌘1** | Single view |
| **⌘2** | Columns view |
| **⌘3** | Rows view |
| **⌘4** | Grid view |
| **⌘,** | Settings |
| **⌘Q** | Quit GATE22 |

Terminal-specific shortcuts such as `Ctrl+C`, `Ctrl+D`, `Tab`, arrows, and shell key combinations continue to go to the active terminal.

## Basic usage

### Open a local shell

Click the **+** button in the tab bar or press **⌘T**.

### Create an SSH connection

1. Click **New Connection** in the sidebar.
2. Enter the host, username, port, and optional identity file.
3. Optionally save the password securely in macOS Keychain.
4. Connect.

Saved connections remain available in the sidebar.

### Use multiple terminals at once

1. Open several local or SSH sessions.
2. Choose **Columns**, **Rows**, or **Grid** from the View control.
3. Click any terminal or its tab to focus it.

### Broadcast a command

1. Switch to Columns, Rows, or Grid.
2. Select the sessions that should receive the same input.
3. Enable **Broadcast** in the session action bar.
4. Type in the focused terminal.

Disable Broadcast when finished.

## Security

GATE22 does not store SSH passwords in connection JSON files.

Saved SSH passwords are stored in the macOS Keychain and delivered to OpenSSH through a hardened local AskPass flow.

Release builds are:

- signed with Apple Developer ID
- built with Hardened Runtime
- notarized by Apple
- distributed in signed and notarized DMGs

See [SECURITY.md](SECURITY.md) for security reporting and implementation details.

## Privacy

GATE22 is local-first.

It currently has:

- no GATE22 cloud account
- no GATE22 cloud sync
- no GATE22 backend
- no advertising SDK

Local configuration stays on the Mac.

Network access is used for:

- SSH sessions explicitly opened by the user
- Sparkle update checks and downloads
- commands and applications run inside terminal sessions

See [PRIVACY.md](PRIVACY.md).

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
