# OpenMind Studio

**Portable-first desktop development environment for Windows and Linux.**

OpenMind Studio combines a Monaco-based code editor, integrated terminal, debugging, Git tooling, extensions, language runtimes, a built-in web preview, and a workspace-aware coding assistant with **OpenMind Cloud** integration. It is designed for everyday development, removable drives, and shared university or office computers.

**Latest release: [v1.0.4](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4) — 21 October 2026**

[Download v1.0.4](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4) · [What's new](RELEASE.md) · [Package checksums](SHA256SUMS.txt) · [Build and signing status](RELEASE-REPORT.md) · [Previous releases](https://github.com/smshagor-dev/OpenMind-Studio/releases)

## Download

Download files only from the [official GitHub release](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4). This release provides 12 Windows and Linux packages across x64 and x86 architectures.

### Windows

| Architecture | Installer EXE | MSI | Portable ZIP |
| --- | --- | --- | --- |
| x64 (recommended) | [Setup EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x64_setup.exe) | [MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x64.msi) | [Portable ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x64_portable.zip) |
| x86 (32-bit) | [Setup EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x86_setup.exe) | [MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x86.msi) | [Portable ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_windows_x86_portable.zip) |

**Installation guidance:** Choose Setup EXE for a standard install, MSI for managed deployment, or ZIP if you need a portable copy. Some Windows x86 language tools and Runtime Manager downloads require 64-bit Windows; choose x64 wherever possible.

### Linux

| Architecture | DEB | AppImage | Portable archive |
| --- | --- | --- | --- |
| x64 | [DEB](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x64.deb) | [AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x64.AppImage) | [Portable tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x64_portable.tar.gz) |
| x86 | [DEB](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x86.deb) | [AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x86.AppImage) | [Portable tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.4/OpenMind-Studio_1.0.4_linux_x86_portable.tar.gz) |

Linux systems may need GTK/WebKitGTK dependencies. Bundled Windows language tools and Runtime Manager downloads are not included in the Linux builds.

**macOS:** Build tooling and a launcher script are available, but **no macOS application package was produced for v1.0.4**. The `.command` asset is not an installer.

## What's new in v1.0.4

### Coding assistant and OpenMind Cloud

- Project-aware chat to inspect, explain, search, and propose code changes, with confirmation before potentially destructive operations.
- Workspace-aware tasks, a task queue, conversation history, attachments, Undo, and slash-command workflows.
- **OpenMind Cloud** support through a user-supplied Developer API key and configurable service endpoint; cloud access requires successful configuration and connectivity.
- A guided AI setup experience and smoother streaming responses. Availability of individual tools depends on runtime configuration and permissions.

### Editor and language tools

- Expanded right-click menu with Go to, Peek, Rename, Refactor, Format, source-control history, compare, blame, and assistant actions.
- PascalABC.NET and Free Pascal compiler selection, NASM assembly tools, language-server assistance and debugging.
- Additional bundled offline formatters, including Prettier integrations, Ruff, gofmt, clang-format, and StyLua.
- Built-in browser panel with a developer console, local HTML/JavaScript previews, SCSS/Sass handling, and reload on save.

### Shared PCs and network deployment

- Network discovery and explicit trust for shared installations and verified package transfers.
- Portable profiles isolated per computer, including databases, settings, and logs.
- Safer cross-computer runtime and language tool installations, UNC path handling, and in-place Windows Update/Repair.
- A 20-point network deployment diagnostic report for IT administrators.
- Room-code collaborative editing remains an **early preview**, pending physical multi-PC and classroom validation.

For detailed fixes, security changes, and compatibility notes, see [Release Notes](RELEASE.md).

## Install and update safely

**v1.0.4 is published but unsigned.** Windows Authenticode and Linux GPG signing have not been applied to these packages. Windows may display security warnings, and some managed devices can block unsigned applications. Follow your organization's installation policies.

The automatic-update interface exists, but **v1.0.4 has no signed update feed**, so download and install the update manually. Keep your existing installation type when upgrading, and back up important projects first. For shared network installations, ensure everyone closes the app before replacing the program files.

Verify your package using [SHA256SUMS.txt](SHA256SUMS.txt). SHA-256 verifies integrity; it does not by itself establish publisher authenticity.

## Privacy and security

OpenMind Studio keeps editor settings, project indexes, and local history in its configured local or per-machine storage. When you use **OpenMind Cloud**, prompts and any project context or attachments selected for the request are sent to the configured online service. Do not send sensitive materials without reviewing what is included.

Windows credentials are protected with DPAPI as documented; equivalent encryption is not yet available for stored secrets on Linux/macOS. See [Privacy Policy](PRIVACY-POLICY.md), [License Agreement](EULA.md), [Terms of Use](TERMS-OF-USE.md), and [Third-party Licenses](THIRD-PARTY-LICENSES.txt).

## Release availability

| Version | Status | Notes |
| --- | --- | --- |
| [v1.0.4](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4) | Published · latest | New coding assistant, OpenMind Cloud integration, expanded tools and network deployment |
| [v1.0.3](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.3) | Previous release | Collaboration preview, browser, installer and multi-PC reliability |
| [Earlier releases](https://github.com/smshagor-dev/OpenMind-Studio/releases) | Historical | Previous releases and archived assets |

## Repository, license and developer

This public repository provides OpenMind Studio release information and downloadable builds. The application source and private signing configuration are maintained separately; this repository is not the full desktop application source.

**License:** [Apache License 2.0](LICENSE) · **Developer:** [Md Shahanur Islam Shagor](https://github.com/smshagor-dev) · **Website:** [smshagor.com](https://smshagor.com)
