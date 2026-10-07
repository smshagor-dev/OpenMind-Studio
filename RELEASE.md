# OpenMind Studio v1.0.1

**Published:** 7 October 2026  
**Channel:** Stable  
**Platforms:** Windows and Linux  
**Architectures:** x64 and x86  
**License:** Apache-2.0

OpenMind Studio v1.0.1 is a major stability, tooling, portability and architecture update focused on restricted-PC development, offline tooling, multi-language support, real-time state synchronization and reliable runtime/tool management.

## Downloads

### Windows

| Architecture | EXE | MSI | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [OpenMind-Studio-Setup-1.0.1-x64.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Setup-1.0.1-x64.exe) | [OpenMind-Studio-1.0.1-x64.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-1.0.1-x64.msi) | [OpenMind-Studio-Portable-1.0.1-x64.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-1.0.1-x64.zip) |
| x86 | [OpenMind-Studio-Setup-1.0.1-x86.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Setup-1.0.1-x86.exe) | [OpenMind-Studio-1.0.1-x86.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-1.0.1-x86.msi) | [OpenMind-Studio-Portable-1.0.1-x86.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-1.0.1-x86.zip) |

**Recommended:** use the EXE installer for most Windows systems and restricted university/office PCs. MSI may require Administrator permission. Use the portable ZIP when a normal installation is not practical.

### Linux

| Architecture | DEB | AppImage | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [OpenMind-Studio-x64.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x64.deb) | [OpenMind-Studio-x64.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x64.AppImage) | [OpenMind-Studio-Portable-linux-x64.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-linux-x64.zip) |
| x86 | [OpenMind-Studio-x86.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x86.deb) | [OpenMind-Studio-x86.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x86.AppImage) | [OpenMind-Studio-Portable-linux-x86.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-linux-x86.zip) |

For Linux, AppImage is the recommended portable package. DEB integrates with Debian/Ubuntu-style systems. The Linux portable ZIP is intentionally small and expects compatible GTK/WebKit and related libraries on the host.

## v1.0.0 → v1.0.1

### New

- **Canonical Rust Live Sync** for runtimes, tools, LSP state, extensions, Git, dependencies, project/debug state, servers and ports across application windows.
- **External filesystem watching** for runtime/tool directories, language servers, extensions, virtual environments, dependency folders and Git changes.
- **C / C++ / Java / Rust Run Code** compile → run pipelines.
- **Portable Tkinter/Tcl-Tk add-on** for Python.
- **Fortran + Pascal support** with portable toolchain/LSP integration.
- **Assembly support** with NASM x86/x64, GAS, asm-lsp and GDB terminal debugging.
- **Offline LSP bundle on Windows**, including Pyright, TypeScript tooling, YAML, Dockerfile, rust-analyzer, clangd and related language tools.
- **Bundled offline formatters on Windows**, including Prettier + plugins, Ruff, gofmt, clang-format and StyLua.
- **Unified Language Tools installation** through Runtime Manager / Language Tools.
- **Unified terminal download broker** for pip, npm, pnpm, Yarn, Git, Go, Cargo, Composer and rustup workflows.
- **Unified MySQL control** for MariaDB + phpMyAdmin under one lifecycle.
- **Server tray mode** while PHP/MySQL services are running.
- **Linux release packages** for x64 and x86: DEB, AppImage and portable ZIP.
- Installer/release-readiness improvements, profile/keybinding work and icon-theme foundations.

### Updated

- Runtime Manager expanded with additional portable runtimes/toolchains and one-click installation paths.
- Terminal PATH/runtime environment refreshes without restarting OpenMind Studio.
- Language Tools now coordinates Run, Format, LSP and debugger/tool status.
- Git, dependencies, project status and debugger state are shared per workspace instead of independently per window.
- PHP control was simplified to a clearer **PHP + MySQL** model.
- Multi-window state handling and workspace isolation were significantly improved.
- Download/network behavior was hardened for restricted and university networks with resumable downloads, checksums and authenticated proxy handling.
- Release packaging now covers Windows EXE/MSI/portable ZIP and Linux DEB/AppImage/portable ZIP.

### Fixed

- New or renamed files not appearing correctly in Explorer.
- Save As / extension changes such as `.txt → .py` leaving syntax highlighting as Plain Text.
- Extension-added languages not recoloring already-open files.
- Node installed but npm unavailable because of terminal/runtime PATH resolution.
- Duplicate watcher events and unnecessary refreshes.
- Stale state, workspace attach/detach races and closed-folder state resurrection.
- Canonical revision-gap recovery bugs.
- Temporary runtime/tool read errors incorrectly appearing as “not installed”.
- Package/install staging directories causing false dependency updates.
- Proxy 407 authentication errors being reported incorrectly.
- Proxy passwords being exposed in command arguments.
- npmrc/temp cleanup issues, watcher recovery issues, shutdown/process leaks and synchronization race conditions.

## Platform notes

### Windows

Windows is the primary full portable/offline-tooling edition in v1.0.1. The Windows packages include the additional offline language-server/formatter tooling and portable runtime assets that make the installers and portable ZIP substantially larger than Linux DEB/ZIP packages.

Windows v1.0.1 is **Authenticode test-signed** with the self-signed `CN=OpenMind` certificate and a DigiCert timestamp. The EXE/MSI installers are signed, and the portable ZIP packages contain a signed `OpenMindStudio.exe`. The Tauri updater `.sig` files remain valid after signing.

Because `CN=OpenMind` is self-signed, this is not a publicly trusted production code-signing certificate. PCs that do not trust the certificate may still show SmartScreen or trust warnings. Public warning-free distribution requires a certificate issued by a trusted code-signing certificate authority.

### Linux

Linux v1.0.1 provides the editor and core desktop experience, but the full Windows offline language-server/formatter bundle, offline Python package and Runtime Manager download set are not currently bundled for Linux.

- DEB installs the application into the normal system layout and uses system dependencies such as WebKitGTK/GTK.
- AppImage bundles more runtime libraries, so it is larger than the DEB/portable ZIP.
- Portable ZIP keeps data beside the application when writable.
- Installed DEB/AppImage builds use the normal Linux application-data location when the application directory is not writable.
- Windows DPAPI secret encryption is not available on Linux; v1.0.1 does not yet provide an equivalent OS-backed secret store there.

## Verification

SHA-256 values for all published v1.0.1 artifacts are recorded in [`SHA256SUMS.txt`](SHA256SUMS.txt). Artifact sizes and hashes are also listed in [`RELEASE-REPORT.md`](RELEASE-REPORT.md).

Release page: https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1
