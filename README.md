# SheepTerm for Windows

A native terminal client for network engineers: **SSH, serial consoles and local shells** in tabs and split panes, with per-vendor
output highlighting, saved hosts, snippets, session logs and optional end-to-end encrypted sync through *your own* Google Drive.
It is the Windows sibling of [SheepTerm for macOS](https://github.com/bestonehxh/SheepTerm) and shares its terminal emulator and SSH client.

## Download

Go to the [latest release](https://github.com/bestonehxh/SheepTerm-Windows/releases/latest) and download
`SheepTerm-Portable-<version>-<build>.zip` (for example `SheepTerm-Portable-0.1-1.zip`). Windows 10 or 11, 64-bit (x64).
The file next to it, `...zip.sig`, is the signature the built-in updater checks; you do not need it to run the app.

1. Unzip the folder **somewhere of your own** (Documents, an `Apps` folder) - not Downloads or the Desktop.
2. Run `SheepTerm.exe`. No installer, no administrator rights, nothing written to the registry or `%APPDATA%`.

### Windows SmartScreen

SheepTerm is not code-signed with a paid certificate yet, so the first run may show "Windows protected your PC".
Click **More info**, then **Run anyway**. Updates are verified another way: every release zip is signed with an Ed25519 key and
the app refuses an update whose signature does not match the key built into it.

## Portable, and where your data lives

Everything SheepTerm stores goes into a `Data\` folder **beside `SheepTerm.exe`**: hosts, settings, snippets, `known_hosts`,
session logs and the encrypted password vault. Copy or move the whole `SheepTerm Portable` folder to take it all with you
(the folder must be writable, so not `Program Files`). Passwords are never stored in clear text; the vault needs your passphrase.
**Help > Check for Updates...** downloads a new release, checks its signature and replaces the program files; `Data\` is never touched.

## Licences

SheepTerm for Windows includes, with their licences in the `Licenses\` folder of the download:

- Inter and JetBrains Mono fonts - SIL Open Font License 1.1
- Lucide icons - ISC License
- swift-crypto (BoringSSL) and swift-asn1 - Apache License 2.0
- The Swift runtime and Foundation - Apache License 2.0 with Runtime Library Exception

The application itself is (c) its author; see the release notes for details. Feedback and bug reports: open an issue on this repository.
