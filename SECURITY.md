# Security

Security is a core requirement for GATE22 because the application manages terminal sessions, SSH connections, and optional saved credentials.

## Reporting a security issue

Please do **not** report vulnerabilities, credentials, private keys, host details, or other sensitive information in a public GitHub issue.

If you discover a security issue, contact the maintainer privately through the GitHub account associated with this repository. A dedicated security reporting channel may be added later.

## Credential storage

Saved SSH passwords are stored in the macOS Keychain.

GATE22 does not store SSH passwords in:

- connection JSON files
- UserDefaults
- command-line arguments
- environment variables
- logs

The Keychain items are configured as non-synchronizing local items.

## SSH password delivery

Saved passwords are supplied to OpenSSH through GATE22's compiled AskPass flow.

The helper:

- has no direct Keychain password-reading capability
- communicates with the running GATE22 application over a private local Unix-domain socket
- is validated by process identity and code-signing identity
- is tied to the exact live `/usr/bin/ssh` parent PID for the active terminal session
- fails closed if session, process, prompt, or identity validation fails

The main GATE22 process remains the only component that reads the saved password from Keychain.

## Local shell

GATE22 intentionally runs outside the macOS App Sandbox so local `zsh` behaves like a normal local terminal.

Release builds retain Hardened Runtime and are signed with an Apple Developer ID certificate and notarized by Apple.

## Updates

GATE22 uses Sparkle 2.

Updates are:

- delivered over HTTPS
- described by the public Sparkle appcast
- protected by Sparkle EdDSA signatures
- distributed as Apple Developer ID signed and notarized builds

## Data integrity

Saved connection data is written atomically.

If the saved-connections JSON exists but is unreadable or corrupt, GATE22 preserves the original data, creates a timestamped backup, and blocks automatic connection/folder persistence writes until a valid reload restores a safe state.
