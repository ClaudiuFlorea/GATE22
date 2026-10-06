# Privacy

GATE22 is designed as a local-first macOS application.

## Local data

GATE22 stores application configuration locally on the Mac, including:

- saved SSH connection metadata
- connection folders
- appearance preferences
- SSH configuration path preference

Saved SSH passwords are stored separately in the macOS Keychain.

## No GATE22 cloud account

GATE22 currently has:

- no GATE22 user account
- no GATE22 cloud sync
- no GATE22 application backend
- no advertising SDK

## Network activity

GATE22 makes network connections when required for functionality:

- SSH connections explicitly opened by the user
- Sparkle update checks and downloads
- other network activity initiated by commands running inside terminal sessions

SSH traffic is handled by the system OpenSSH client.

## SSH configuration

If enabled, GATE22 reads SSH configuration metadata from the configured SSH config file for display and launch purposes. GATE22 does not modify that file.

## Updates

Sparkle checks the public GATE22 update feed hosted through GitHub and downloads update artifacts from GitHub Releases.
