# OpenMind Studio

**Portable-first desktop development environment for Windows and Linux.**

OpenMind Studio combines a Monaco-powered code editor, integrated terminal, debugging, Git, language runtimes, extensions, a built-in browser, and AI-assisted coding through local models or optional **OpenMind Cloud**.

## Latest release

**[OpenMind Studio v1.0.5 — October 27, 2026](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.5)**

This update expands VS Code extension import and execution, improves editor and session recovery, refines OpenMind AI Cloud settings, and adds Windows PascalABC.NET integration. Read the [full release notes](RELEASE.md).

## Downloads

Only the files actually published with v1.0.5 are linked below.

### Windows 64-bit

| Format | Download | Best for |
| --- | --- | --- |
| Setup EXE | [Download EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMind.Studio_1.0.5_x64-setup.exe) | Standard per-user installation |
| MSI | [Download MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMind.Studio_1.0.5_x64_en-US.msi) | Managed installation |
| Portable ZIP | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMindStudio-1.0.5-portable-win-x64.zip) | Portable use and restricted PCs |

### Linux 64-bit

| Format | Download |
| --- | --- |
| Debian package | [Download DEB](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMind-Studio_1.0.5_linux_x64.deb) |
| AppImage | [Download AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMind-Studio_1.0.5_linux_x64.AppImage) |
| Portable archive | [Download tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.5/OpenMind-Studio_1.0.5_linux_x64_portable.tar.gz) |

**Not available in this release:** x86 packages and macOS application installers. Previous releases may have other architectures or formats.

## What's new in v1.0.5

- **VS Code extension compatibility:** importing and running supported extensions, better ESM support, editor APIs, language integrations, debugger/task interfaces, and extension lifecycle behavior.
- **Editor reliability:** recovery for unsaved and virtual documents, safer Save As behavior, separate recovery per window, and flushing pending changes before exit/update.
- **OpenMind AI Cloud:** redesigned provider settings and removed desktop-side prompt/generation caps where supported (provider/model limits still apply).
- **Language tooling:** PascalABC.NET integration for Windows and improved ZIP Cyrillic filename compatibility.
- **Bug fixes:** extension activation races, file permission handling, document provider ownership, snippet insertion validation, editor decorations, and debugging cleanup.

See [RELEASE.md](RELEASE.md) for details, compatibility limitations, and upgrade guidance.

## Features

- Monaco code editor with tabs, split views, file search, Markdown and other previews.
- Integrated terminal, Run Code, debugging, tasks, and notebook tools.
- Git integration and a supported subset of VS Code/Open VSX extensions.
- Portable runtimes and language tools on supported systems.
- Local AI and optional OpenMind Cloud; online requests transmit selected content to the configured provider.
- Collaboration features (preview) and shared-computer deployment workflows.

## Install and update safely

1. Save work and close OpenMind Studio.
2. Download the matching asset from the official release above.
3. Install or replace the program files for your existing installation type; preserve your data.
4. Check your workspaces, settings, and extensions after upgrading.

**Signing and verification:** The GitHub v1.0.5 asset list does not include standalone updater `.sig` files or a `latest.json` feed. Do not assume automatic updates are available. A checksum of a downloaded asset can detect corruption when compared with an independently trusted value; the repository's existing `SHA256SUMS.txt` and historical [v1.0.4 report](RELEASE-REPORT-v1.0.4.md) are not verification manifests for v1.0.5. Windows Authenticode signing must be verified on the actual executable before claiming publisher trust.

Linux applications require compatible system libraries, including GTK/WebKitGTK; the supported glibc baseline depends on the build environment.

## Previous releases

- [v1.0.4](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4) · [Archived notes](RELEASE-v1.0.4.md) · [Archived artifact report](RELEASE-REPORT-v1.0.4.md)
- [v1.0.3](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.3)
- [All releases](https://github.com/smshagor-dev/OpenMind-Studio/releases)

## Legal, privacy, and source

- [License Agreement](EULA.md)
- [Privacy Policy](PRIVACY-POLICY.md)
- [Terms of Use](TERMS-OF-USE.md)
- [Third-party Notices](THIRD-PARTY-LICENSES.txt)

This public repository hosts release packages and documentation. The application source and private signing material are maintained in a separate private repository.

**License:** Apache-2.0 · **Developer:** [Md Shahanur Islam Shagor](https://github.com/smshagor-dev) · **Website:** [smshagor.com](https://smshagor.com)
