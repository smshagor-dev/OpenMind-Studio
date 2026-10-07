# OpenMind Studio

**OpenMind Studio** is a portable desktop IDE for **Windows and Linux**, built for students, developers, university labs, office PCs, shared systems, and other restricted environments where administrator access or global development-tool installation may not be available. Windows remains the primary full portable/offline-tooling edition, while v1.0.1 adds Linux packages for x64 and x86.

It is a native desktop application built with **Rust, Tauri 2, React, TypeScript, Vite, and Monaco Editor**. The goal is to provide a practical local development workspace with editing, terminals, portable runtimes, language tooling, source control, previews, local servers, database tooling, extensions, and optional AI integrations without depending on a fully configured system-wide development machine.

## Download v1.0.1

**Latest stable release:** [OpenMind Studio v1.0.1](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1)

### Windows

| Architecture | EXE installer | MSI installer | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [Download EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Setup-x64.exe) | [Download MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x64.msi) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-x64.zip) |
| x86 | [Download EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Setup-x86.exe) | [Download MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x86.msi) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-x86.zip) |

> **Windows installer note**
>
> The **EXE installer is recommended** for most users and restricted university/office PCs. MSI packages may require Administrator permission depending on Windows or organization policy. The portable ZIP is available when installation is not practical.

### Linux

| Architecture | DEB | AppImage | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [Download DEB](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x64.deb) | [Download AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x64.AppImage) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-linux-x64.zip) |
| x86 | [Download DEB](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x86.deb) | [Download AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-x86.AppImage) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.1/OpenMind-Studio-Portable-linux-x86.zip) |

For Linux, the **AppImage is the recommended portable package**. The DEB package integrates with Debian/Ubuntu-style systems and uses system GTK/WebKit dependencies. The portable ZIP is lightweight and also depends on compatible system libraries.

See [`SHA256SUMS.txt`](SHA256SUMS.txt) for release hashes and [`RELEASE-REPORT.md`](RELEASE-REPORT.md) for artifact details.

---

## Current release

**Version:** `1.0.1`  
**Channel:** Stable  
**Platforms:** Windows 10/11 and Linux  
**Architectures:** x64 and x86 release assets  
**License:** Apache License 2.0 (`Apache-2.0`)

Release binaries are published through **GitHub Releases**, not committed to the source branch.

Available release formats:

- Windows NSIS setup `.exe`
- Windows Installer `.msi`
- Windows portable `.zip`
- Linux `.deb`
- Linux AppImage
- Linux portable `.zip`

Windows provides the fullest portable/offline tooling experience in v1.0.1. Linux packages provide the editor and core desktop experience, but some offline bundles and Runtime Manager download workflows remain Windows-only.

---

## Designed for restricted PCs

OpenMind Studio is especially useful on:

- university computers
- computer labs
- office PCs
- shared Windows systems
- training centers
- systems where users do not have administrator rights
- machines where global PATH changes are not permitted
- portable or temporary development workstations

The application prefers **app-local runtimes and tools** and avoids changing the User or Machine `PATH` for normal workflows.

OpenMind Studio does not intentionally bypass operating-system, firewall, proxy, authentication, administrator, or institutional security controls.

---

## Editor and workspace

OpenMind Studio provides a VS Code-style desktop editing workflow built around Monaco Editor.

Current editor/workspace features include:

- multi-file Monaco editor
- editor tabs
- split editor workflow
- file explorer
- breadcrumbs
- recent files and folders
- workspace/session restore
- encoding-aware file handling
- application menus
- keyboard shortcuts
- settings UI
- status bar
- themes
- icon themes
- profiles
- Problems panel
- Output panel
- Debug Console panel
- Terminal panel
- Ports panel
- Search interface
- Run and Debug interface
- Remote Explorer foundation
- Extensions interface

The editor also includes common tab and editor actions such as preview, split, close, lock, and reopen workflows.

---

## Run Code

OpenMind Studio includes a **Run Code** workflow for supported languages and project types.

It resolves OpenMind-managed tools before system fallbacks where possible and launches code with an app-local development environment instead of requiring users to manually configure global tool paths.

The Run Code system integrates with runtime detection, tasks, terminals, project detection, and the application toolchain resolver.

---

## Integrated terminal

The integrated terminal supports local project work while exposing OpenMind-managed runtimes and tools to launched terminal sessions.

Key behaviors:

- portable runtimes are preferred where configured
- environment variables are injected per process/session
- global User/Machine `PATH` is not modified
- multiple development stacks can coexist inside the application environment
- terminal networking is not transparently redirected for arbitrary user programs

Supported tool areas include Python, Node.js, npm, pnpm, PHP, Composer, Git, Go tooling where configured, and other app-managed development tools.

---

## Runtime Manager

OpenMind Studio includes a portable Runtime Manager for downloading, installing, detecting, repairing, and using development runtimes inside the application environment.

> **Platform note:** the full Runtime Manager download workflow and bundled offline runtime/tool packages in v1.0.1 are primarily available on Windows. Linux builds do not currently include the Windows-only offline Python, LSP/formatter bundles, or the same Runtime Manager download set.

Current runtime/tool areas include:

### Node.js

- portable Node.js runtime
- npm support
- pnpm support
- runtime detection and selection
- app-local command resolution

### Python

- portable Python runtime
- pip support
- Python package workflows
- runtime detection and selection

### Git

- portable Git
- source-control integration
- app-local Git resolver
- Git operations without requiring a normal machine-wide Git install

### PHP

Portable PHP runtime support covering the PHP 8.x line used by the Runtime Manager, including supported 8.0–8.4 packages where available.

### Composer

- portable Composer support
- PHP dependency-management workflows
- integration with the local PHP toolchain

### MariaDB

- app-managed local MariaDB environment
- start/stop/restart controls
- local database development workflow

### phpMyAdmin

- local phpMyAdmin integration
- browser-based database-management workflow tied to the local PHP/MariaDB stack

### Go and additional toolchains

The toolchain system includes support for resolving additional development tools and manifests, including Go-related workflows where configured.

---

## Optional workload installation

OpenMind Studio is designed so the base application can be installed without forcing every runtime onto the machine.

Users can install only the workloads they need, such as:

- Python
- Node.js
- PHP
- Git
- Composer
- MariaDB
- phpMyAdmin
- language-server packs
- formatters
- linters
- debugging/toolchain components

This keeps the base installation smaller and makes the environment practical for university and office PCs.

---

## Language Server Protocol (LSP)

OpenMind Studio includes an LSP foundation for editor intelligence and language-aware tooling.

Core/current language areas include:

- TypeScript
- JavaScript
- JSON
- HTML
- CSS
- Python where the configured language server/tooling is available
- PHP where the configured language server/tooling is available

The LSP/toolchain system supports app-local language-server discovery and installation flows. Additional language-server packs can be added without requiring normal system-wide installation.

Editor intelligence foundations include diagnostics, symbols, navigation/reference workflows, and language-aware integration where supported by the configured server.

---

## Formatting, linting, and code quality

OpenMind Studio includes formatting infrastructure for common project types.

Current capabilities include:

- Format Document
- Format on Save
- built-in JSON/package.json formatting
- formatter discovery
- app-managed formatter/tool resolution
- clear missing-tool messages
- language/toolchain contribution support

Formatter, linter, and language-tool availability depends on the selected workload and project stack.

---

## Git and source control

The Source Control area provides Git integration with preference for OpenMind-managed Git when available.

Features include:

- repository detection
- source-control view
- app-local Git resolution
- terminal Git integration
- project Git workflows without requiring a global Git installation

The application does not need to rewrite system Git configuration just to provide source-control access.

---

## PHP local development stack

OpenMind Studio includes an integrated PHP development environment intended to work on machines where users cannot install a normal local server stack globally.

Included areas:

- portable PHP runtimes
- PHP built-in server workflow
- Composer
- MariaDB
- phpMyAdmin
- Laravel helper workflow
- local server controls
- port management
- database credential handling

Database passwords are masked by default and can be revealed/copied by explicit user action.

OpenMind Studio does not automatically overwrite a project's `.env` file without user action.

---

## Preview system

Read-only previews are available for common development and document files.

Supported preview areas include:

- PNG
- JPG / JPEG
- WebP
- GIF
- BMP
- SVG
- PDF
- DOCX
- XLSX
- CSV
- Markdown
- HTML
- LaTeX source

Unsupported or binary files use safe fallback messaging instead of being incorrectly loaded as text.

---

## Workspace search and project detection

OpenMind Studio includes workspace search/indexing foundations and project detection for common development stacks.

Detected/project-oriented areas include:

- HTML/CSS/JavaScript
- TypeScript
- React
- Vite
- Next.js-style projects
- Node.js
- Python
- PHP/Laravel
- Rust
- Go
- Docker
- SQL/database projects
- Markdown
- JSON
- YAML
- TOML
- mixed-language projects

---

## Extensions

OpenMind Studio includes an extension platform foundation.

Current contribution areas include:

- local VSIX installation
- enable / disable
- uninstall
- commands
- keybindings
- menus
- languages
- snippets
- themes
- activity-bar views
- tree views
- status-bar items
- WebviewPanel support
- extension settings/contributions
- permission guarding

OpenMind Studio does not currently claim full VS Code API compatibility. Advanced APIs such as complete notebook, terminal, task, WebviewView, and debug-extension parity remain ongoing areas of development.

---

## Optional AI providers

AI is optional. The editor works without an AI provider.

The provider architecture includes paths for:

- Claude
- OpenAI / OpenAI-compatible APIs
- Gemini
- local loopback OpenAI-compatible providers

Security/privacy behavior includes:

- Windows DPAPI-backed API-key storage; Linux v1.0.1 does not yet provide equivalent OS-backed secret encryption
- no hidden AI request at application launch
- no AI panel unless a provider is configured/enabled
- confirmation-aware online content sending

---

## Network and download resilience

OpenMind Studio includes a download broker and local gateway for application-managed runtime/tool downloads.

The broker provides:

- shared downloads when multiple components request the same file
- progress reporting
- cancellation
- resume support
- temporary-directory management
- startup cleanup
- structured download errors
- proxy-aware application downloads
- checksum verification
- package integrity verification

The local gateway:

- listens only on `127.0.0.1`
- uses a random per-run token
- validates requested hosts
- keeps HTTPS certificate validation enabled
- verifies SHA-256 hashes where supported

Supported application-managed network workflows include areas such as:

- pip
- npm
- pnpm
- Git
- runtime/tool downloads
- language-server installation
- selected tasks and Run Code tooling
- Composer/Cargo-related routed workflows where configured

User applications and arbitrary user traffic are not transparently routed through the gateway.

Institutional proxy/firewall policies can still prevent external repositories from being reached. OpenMind Studio is designed for resilience, not security-control bypass.

---

## Updater

OpenMind Studio v1.0.1 includes application-update infrastructure.

Official update metadata is expected from GitHub Releases through the configured updater endpoint.

Updater artifacts are cryptographically signed, and the application verifies update signatures against the embedded updater public key before accepting an update.

The private signing key must never be committed to the repository.

---

## Privacy and security model

OpenMind Studio is local-first by design.

Key principles:

- no global runtime installation required for normal portable workflows
- no User/Machine `PATH` mutation for app-managed tools
- no hidden AI requests
- no automatic project upload
- API keys are not intentionally written to logs
- database passwords are masked by default
- extension permissions are guarded
- network actions are user/workflow driven
- updater artifacts are signature verified
- package hashes are verified where available
- internal gateway binds to localhost only

Third-party package managers, Git remotes, AI providers, and external services have their own policies and network behavior.

---

## Installation

Download the current packages from the project's [GitHub Releases](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1) page.

### Windows EXE

Use the NSIS `.exe` installer for normal installation. This is the recommended option for most Windows users and for many restricted PCs.

### Windows MSI

Use the `.msi` package when Windows Installer or managed deployment is preferred. Administrator approval may be required depending on Windows, domain, university, or office policy.

### Windows portable ZIP

Extract the archive and run OpenMind Studio without a normal installer. This is useful where installation is restricted.

### Linux DEB

Use the `.deb` package on compatible Debian/Ubuntu-based systems. Installation normally uses the system package manager and may require `sudo`.

### Linux AppImage

The AppImage is the recommended portable Linux package. Make it executable and launch it directly.

### Linux portable ZIP

Extract and launch the included binary. This package is smaller because compatible GTK/WebKit and other system libraries are expected to be present on the host.

---

## System requirements

Recommended baseline:

- Windows 10 / 11 or a compatible modern Linux distribution
- x64 recommended; x86 release assets are also published
- 4 GB RAM minimum
- 8 GB RAM or more recommended
- enough storage for selected runtimes and workloads
- Windows: WebView2 runtime available on the system
- Linux DEB/ZIP: compatible GTK 3 and WebKitGTK 4.1 libraries
- internet access for runtime/tool downloads when those workflows are used

Runtime/tool workloads require additional disk space. Windows packages are larger because v1.0.1 includes additional offline/runtime tooling that is not bundled into the Linux DEB/ZIP builds.

---

## Development setup

Prerequisites for building OpenMind Studio from source:

- Rust toolchain
- Node.js
- pnpm
- Windows build requirements for Tauri/MSVC packaging

Install frontend dependencies:

```sh
pnpm install
```

Run development mode:

```sh
pnpm tauri dev
```

Useful validation commands:

```sh
cargo fmt --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace

pnpm lint
pnpm test
pnpm build
```

---

## Release build

Production release workflow:

```sh
pnpm release:build
```

For signed updater builds, the required Tauri updater signing environment variables must be configured locally or in the release environment. Private signing material must never be committed.

Release binaries belong in **GitHub Releases**, not the source branch.

---

## Project structure

```text
crates/       Rust domain crates and backend systems
src-tauri/    Tauri desktop shell, commands, updater, and Windows integration
src/          React + TypeScript frontend
scripts/      release, packaging, signing, and development tooling
docs/         architecture, release, networking, runtime, and validation documentation
```

---

## v1.0.1 highlights

OpenMind Studio v1.0.1 expands the original release with major stability, portability, language-tooling and synchronization work:

- canonical Rust-backed live state synchronization across windows
- external filesystem watching for runtimes, tools, language servers, extensions, dependencies and Git state
- C, C++, Java and Rust Run Code compile/run pipelines
- portable Python Tkinter/Tcl-Tk add-on
- Fortran and Pascal toolchain integration
- Assembly support with NASM x86/x64, GAS, asm-lsp and GDB terminal debugging
- bundled offline LSP and formatter tooling on Windows
- unified Language Tools installation and status handling
- unified terminal download broker for pip, npm, pnpm, Yarn, Git, Go, Cargo, Composer and rustup workflows
- unified MySQL control for MariaDB + phpMyAdmin
- server tray behavior while PHP/MySQL services are active
- improved terminal runtime/PATH refresh without restarting the app
- stronger multi-window/workspace isolation and shared canonical state
- hardened restricted-network/proxy handling, resumable downloads and checksum verification
- Linux x64/x86 release packages: DEB, AppImage and portable ZIP
- Windows x64/x86 packages: EXE, MSI and portable ZIP

Notable fixes include Explorer refresh issues, Save As language-mode detection, extension language recoloring, Node/npm environment resolution, duplicate watcher events, stale workspace state, revision-gap recovery, temporary install-state errors, proxy authentication reporting, credential exposure in command arguments, cleanup failures and shutdown/process leaks.

For the full v1.0.0 → v1.0.1 changelog and platform notes, see [`RELEASE.md`](RELEASE.md).

---

## Repository policy

The `main` branch contains source code, documentation, configuration, and development assets.

Compiled release packages such as Windows `.exe` / `.msi` / portable ZIP and Linux `.deb` / AppImage / portable ZIP files are published as GitHub Release assets rather than committed directly to `main`.

Signing private keys, passwords, certificates, API secrets, and other private credentials must never be committed.

---

## Author

**Md Shahanur Islam Shagor**  
Founder & Developer, OpenMind Studio  
Independent Researcher & Software Engineer

GitHub: `smshagor-dev`  
Portfolio: `https://smshagor.com`

---

## License

OpenMind Studio is released under the **Apache License 2.0**.

See [`LICENSE`](LICENSE) for the complete license text.
