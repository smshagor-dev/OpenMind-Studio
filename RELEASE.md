# OpenMind Studio v1.0.0

OpenMind Studio is a portable Windows development environment designed especially for university labs, office computers, shared systems, and other restricted PCs where users may not have administrator access or system-wide development tools.

## Download

### x64

- [EXE installer](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x64.exe)
- [MSI installer](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x64_en-US.msi)

### x86

- [EXE installer](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x86.exe)
- [MSI installer](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x86_en-US.msi)

The EXE installer is recommended for most users. MSI is available for managed deployment or environments that prefer Windows Installer packages.

## What v1.0.0 includes

- Monaco-based code editor
- Explorer, editor tabs, breadcrumbs and workspace restore
- Integrated terminal
- Run Code workflow
- Portable Runtime Manager
- Node.js, npm and pnpm
- Python and pip
- Git and Source Control
- PHP 8.x
- Composer
- MariaDB and phpMyAdmin
- Go/toolchain support where configured
- Language Server Protocol foundation
- Format Document and formatter/tool discovery
- Workspace search and project detection
- Image, PDF, DOCX, XLSX, CSV, Markdown and HTML previews
- Local VSIX extension foundation
- Optional Claude, OpenAI/OpenAI-compatible, Gemini and local AI-provider architecture
- Proxy-aware runtime/tool downloads
- Shared/resumable download broker
- Localhost-only package gateway
- SHA-256/package integrity verification
- Signed updater infrastructure
- x64 and x86 Windows packaging
- EXE and MSI release formats

## Designed for university and office PCs

OpenMind Studio is built around application-local runtimes and development tools. This makes it useful on university computers, office PCs, computer labs and shared Windows systems where normal global development-tool installation may not be practical.

Normal app-managed workflows avoid changing the User or Machine `PATH` and do not require every supported runtime to be installed system-wide.

OpenMind Studio does not intentionally bypass operating-system restrictions, administrator controls, authentication, firewall rules, proxy policies or institutional security controls.

## Runtime and language tooling

Supported runtime/tool areas include Node.js, Python, PHP, Git, Composer, MariaDB, phpMyAdmin and additional toolchains such as Go where configured.

The LSP/toolchain system provides the foundation for diagnostics, symbols, navigation, references and other language-aware editor features for supported/configured languages including JavaScript, TypeScript, JSON, HTML, CSS, Python and PHP.

## Networking and updater

Application-managed downloads use the OpenMind Studio download broker and local gateway where supported. The gateway binds to `127.0.0.1`, uses per-run authentication, preserves HTTPS certificate validation and verifies package hashes where available.

Updater artifacts are cryptographically signed and the application verifies updates using its configured updater public key before accepting them.

## Platform

- Windows 10 / 11
- x64 and x86 builds
- Stable release: `v1.0.0`
- License: Apache License 2.0

## Release page

https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.0

For file sizes and SHA-256 hashes, see [`RELEASE-REPORT.md`](RELEASE-REPORT.md).
