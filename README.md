# SheepTerm for Windows

A native terminal client for network engineers: **SSH, Telnet, serial consoles and local shells** in tabs and split panes, with per-vendor
output highlighting, file transfer, Ping, device web UIs, saved hosts, snippets, session logs and optional end-to-end encrypted sync through *your own* Google Drive.
It is the Windows sibling of [SheepTerm for macOS](https://github.com/bestonehxh/SheepTerm) and shares its terminal emulator and SSH client.

[Website](https://sheepterm.com/) · [All features](https://sheepterm.com/features/) · [macOS download](https://github.com/bestonehxh/SheepTerm/releases/latest) · [Windows download](https://github.com/bestonehxh/SheepTerm-Windows/releases/latest) · [Linux download](https://github.com/bestonehxh/SheepTerm-Linux/releases/latest)

English · 简体中文 · 日本語 · 한국어 · Español · Português (Brasil) · Français · Deutsch · Русский

<img src="https://sheepterm.com/assets/win/v0-1-24/main@2x.webp" width="900" alt="SheepTerm on Windows: Cisco output highlighted, beside a sidebar of saved hosts in nested groups">

## Download

| Platform | Download | Requirements |
|---|---|---|
| 🍎 macOS | [**Latest release**](https://github.com/bestonehxh/SheepTerm/releases/latest) | macOS 26.4 (Tahoe) or later, Apple Silicon |
| 🪟 Windows | [**Latest release**](https://github.com/bestonehxh/SheepTerm-Windows/releases/latest) (portable zip) | Windows 10 / 11, 64-bit (x64) |
| 🐧 Linux | [Latest release](https://github.com/bestonehxh/SheepTerm-Linux/releases/latest) (portable tar.gz) | x86_64 or arm64, GTK 4 |


Go to the [latest release](https://github.com/bestonehxh/SheepTerm-Windows/releases/latest) and download
`SheepTerm-Portable-<version>-<build>.zip` (the zip on the latest release is always the newest build). Windows 10 or 11, 64-bit (x64).
The file next to it, `...zip.sig`, is the signature the built-in updater checks; you do not need it to run the app.

1. Unzip the folder **somewhere of your own** (Documents, an `Apps` folder) - not Downloads or the Desktop.
2. Run `SheepTerm.exe`. No installer, no administrator rights, nothing written to the registry or `%APPDATA%`.

### Windows SmartScreen

SheepTerm is not code-signed with a paid certificate yet, so the first run may show "Windows protected your PC".
Click **More info**, then **Run anyway**. Updates are verified another way: every release zip is signed with an Ed25519 key and
the app refuses an update whose signature does not match the key built into it.

## Features

The short version, by area. Every feature is on [sheepterm.com/features](https://sheepterm.com/features/).

### Connections

SSH, serial (COM ports), Telnet and a local shell (Command Prompt, PowerShell 7, Windows PowerShell or WSL), each in its own tab. One box takes `user@host`, a URL, `ping 10.0.0.1` or `sftp://…`.
Sign-in happens on a card inside the tab, with password retry on the same connection and Try Again after a failure. Jump host, local / remote / SOCKS port forwards, auto-reconnect and legacy ciphers for old gear are built in. SSH keys come from files; there is no ssh-agent yet.

<table>
<tr>
<td width="60%"><img src="https://sheepterm.com/assets/win/v0-1-24/quick-connect@2x.webp" alt="Quick Connect searching saved hosts"></td>
<td width="40%"><img src="https://sheepterm.com/assets/win/v0-1-24/new-ssh@2x.webp" alt="The New SSH Connection form"></td>
</tr>
</table>

### Sidebar & groups

Groups inside groups (a site, a building, a floor) in one searchable sidebar. Drag to reorder. Each host keeps its own device family, credential, logging and paging choice.

### Tabs & split panes

Up to nine panes in one tab, in a tidy grid, every pane a full session. Drag a pane header or a tab chip to move or merge; zoom a pane, even them out, or unsplit it back to a tab.

<img src="https://sheepterm.com/assets/win/v0-1-24/panes@2x.webp" width="800" alt="Four panes: Aruba CX, Cisco, Juniper and FortiGate sessions">

### Terminal

Our own emulator with one highlight pack per device family: Cisco, Aruba, Huawei, H3C / HPE, Juniper, Palo Alto, Fortinet, Check Point and Linux. The family is detected from the stream or set per host, and a device's own colours are never overridden.

**Safe Multi-line Paste** previews a paste and sends it line by line, waiting for the device's prompt. **Danger Command Guard** holds `reload`, `write erase` and the like until you press Send. Also: session logs with Search Logs, Auto-page, six themes and Network Info with the ARP table.

### Ping tab

Many hosts at once, in a tab or split beside the console while a device reloads: Status, latency, OK / Failed, rate, a last-minute graph and a packet log to save as CSV. Nothing pings until you add a target.

<img src="https://sheepterm.com/assets/win/v0-1-24/ping@2x.webp" width="800" alt="A Ping tab with four hosts: Fail, Slow and two OK, with latency and rate">

### File Server & Files tab

TFTP, SFTP, SCP and FTP servers in the bottom bar, off until you start them: pick a file and copy the command for your device family. The Files tab browses a device over SFTP, SCP, FTP or TFTP and rides an open SSH tab: no second login, through a jump host too.

<img src="https://sheepterm.com/assets/win/v0-1-24/file-server@2x.webp" width="800" alt="The File Server card with TFTP on and an Aruba CX copy command for the chosen firmware file">

### Web tabs & login key

A device's web page in a tab or pane (WebView2), next to its console. Self-signed certificates are confirmed like host keys. A key inside the login field fills a saved credential; nothing is submitted for you.

### Snippets, Broadcast, Command History

Saved commands with `{{variables}}`, one line typed into every tab you tick, and each host's own history of up to 500 commands with secrets filtered out.

### Sync & security

Passwords live in an encrypted vault opened by your passphrase, never in clear text. Sign in with Google to sync hosts, groups, credentials, snippets and settings between Windows and Mac, end-to-end encrypted with your passphrase, in your own Drive. Off until you sign in.

### AI panel

Ask about the output in front of you with the Claude, ChatGPT or Gemini subscription you already have, through the vendors' own CLIs. Codex and Gemini each run in their own restricted AppContainer. Secrets are removed first, you can see exactly what is sent, and it never runs a command.

### Console cable

Plug in a USB console cable and a card offers Connect at the right speed. The speed is a menu on the open port, wrong-speed text gets a *Garbled? Try 115200* hint, and Send Break and XMODEM / YMODEM are there for a recovery.

### Backup, import & export

Add Hosts from a spreadsheet or CSV, one Backup file (never with passwords), `.sheepterm` group files, and Share Link: a group sealed with a passphrase, kept in your own Drive.

### What's New & updates

Updates are checked against an Ed25519 signature and install only when you press the button. What's New opens once per release, and any time from Help.

## Shortcuts

| Action | Keys |
|---|---|
| Quick Connect | Ctrl+Shift+Q |
| New Terminal Tab | Ctrl+Shift+T or Ctrl+Alt+T |
| New SSH Connection | Ctrl+Shift+N |
| Split Right / Split Down | Alt+Shift+= / Alt+Shift+- |
| Close Pane / Close Tab | Ctrl+Alt+W / Ctrl+Shift+W |
| Next / Previous Tab | Ctrl+Tab / Ctrl+Shift+Tab |
| Tab 1 to Tab 9 | Ctrl+1 to Ctrl+9 |
| Copy / Paste | Ctrl+Shift+C / Ctrl+Shift+V |
| Find / Find Next | Ctrl+Shift+F / F3 |
| Full Screen | F11 |

A bare Ctrl+letter is never an app shortcut, and neither is Alt+letter: Ctrl+A, Ctrl+R, Ctrl+W, Alt+B, Alt+F and the rest reach the shell or the device CLI. That is why Copy and Paste carry Shift. [Every shortcut, Windows and Mac](https://sheepterm.com/features/#shortcuts).

## Languages

Nine languages on both Windows and Mac: English, 简体中文, 日本語, 한국어, Español, Português (Brasil), Français, Deutsch and Русский.

The interface follows the Windows display language and falls back to English. To switch manually, open **Settings > App Language**, then restart SheepTerm.

<img src="https://sheepterm.com/assets/win/v0-1-24/settings@2x.webp" width="520" alt="Settings with App Language, Chrome, Local shell and the terminal font">

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
