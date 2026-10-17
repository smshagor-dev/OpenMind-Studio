# OpenMind Studio

**OpenMind Studio** is a portable desktop IDE for Windows and Linux, built for developers, students and shared university or office computers. It combines Monaco editing, integrated terminals, portable runtimes, language tooling, Git, debugging, file previews, extensions and optional AI assistance.

**Latest published release: v1.0.3** (October 13, 2026) · **Upcoming: v1.0.4** (not published)

[Download v1.0.3](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.3) · [All releases](https://github.com/smshagor-dev/OpenMind-Studio/releases) · [Current release notes](RELEASE.md) · [Release artifact report](RELEASE-REPORT.md)

## Download v1.0.3

### Windows

| Architecture | Setup EXE | MSI | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [OpenMind-Studio_1.0.3_windows_x64_setup.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x64_setup.exe) | [OpenMind-Studio_1.0.3_windows_x64.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x64.msi) | [OpenMind-Studio_1.0.3_windows_x64_portable.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x64_portable.zip) |
| x86 | [OpenMind-Studio_1.0.3_windows_x86_setup.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x86_setup.exe) | [OpenMind-Studio_1.0.3_windows_x86.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x86.msi) | [OpenMind-Studio_1.0.3_windows_x86_portable.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_windows_x86_portable.zip) |

Setup is recommended for normal installations. MSI may require administrator privileges; portable ZIP is useful on restricted computers. No operating-system restrictions should be bypassed.

### Linux

| Architecture | DEB | AppImage | Portable tar.gz |
| --- | --- | --- | --- |
| x64 | [OpenMind-Studio_1.0.3_linux_x64.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x64.deb) | [OpenMind-Studio_1.0.3_linux_x64.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x64.AppImage) | [OpenMind-Studio_1.0.3_linux_x64_portable.tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x64_portable.tar.gz) |
| x86 | [OpenMind-Studio_1.0.3_linux_x86.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x86.deb) | [OpenMind-Studio_1.0.3_linux_x86.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x86.AppImage) | [OpenMind-Studio_1.0.3_linux_x86_portable.tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.3/OpenMind-Studio_1.0.3_linux_x86_portable.tar.gz) |

Linux packages may require system GTK/WebKitGTK libraries. Use the release page to verify available assets and platform requirements. **macOS packages are not included in the published v1.0.3 assets.**

## v1.0.3 highlights

- Collaborative workspace **preview** with room codes, live editing and presence. Real-world multi-computer validation remains limited.
- Built-in browser for frontend development, including saved-page preview and console workflows.
- Automatic update checks and signature verification, with platform-appropriate install policies.
- Windows setup choices for per-user and shared-network deployments, with improved upgrades and repairs.
- Better per-machine data isolation, shared runtime coordination and Linux/Windows packaging.

See the [official v1.0.3 release](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.3) for the complete changelog.

## AI assistance and coding agent

OpenMind Studio has an **existing configurable AI chat/provider integration** in its development architecture. This is distinct from a complete autonomous coding agent, and provider/model availability depends on user configuration.

**AI Coding Agent is upcoming, not confirmed as shipped in v1.0.3 or the prepared v1.0.4 build.** Workspace-wide autonomous changes, multi-file edits, tool execution, approval policies and resumable tasks must not be claimed as released until implementation and packaged-app tests establish that status.

## Upcoming v1.0.4 (not yet published)

The prepared v1.0.4 development release focuses on **Network Deployment** (LAN discovery, explicit trust and verified release packages), shared-installation Desktop shortcut deployment for Windows users, runtime/language-tools concurrency fixes, mapped-drive profile reliability, per-computer cache isolation and network hardening.

Physical testing across multiple university PCs remains pending. Windows installers are not currently trusted Authenticode-signed; Windows security warnings or restrictions may apply. v1.0.4 downloads will appear on [GitHub Releases](https://github.com/smshagor-dev/OpenMind-Studio/releases) only when published.

## About this repository

This public repository hosts OpenMind Studio release information and public download assets. Development source code and private signing material are maintained separately; do not assume this repository contains the complete application source.

**License:** [Apache 2.0](LICENSE) · **Developer:** [Md Shahanur Islam Shagor](https://github.com/smshagor-dev) · [Portfolio](https://smshagor.com)
