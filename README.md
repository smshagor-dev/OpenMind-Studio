# OpenMind Studio

**OpenMind Studio** is a portable desktop IDE for **Windows and Linux**, designed for students, developers, university labs, office PCs, shared systems, and restricted environments where administrator access or global development-tool installation may not be available.

It is built with **Rust, Tauri 2, React, TypeScript, Vite, and Monaco Editor** and provides editing, terminals, portable runtimes, language tooling, Run Code, source control, previews, local servers, database tooling, extensions, and optional AI integrations.

## OpenMind Studio v1.0.2

**Channel:** Stable  
**Platforms:** Windows and Linux  
**Windows architectures:** x64 and x86  
**Linux architecture:** x86_64 / amd64  
**License:** Apache License 2.0

OpenMind Studio v1.0.2 adds safer **multi-computer portable use**. One portable OpenMind Studio installation can be used across many computers while keeping runtimes and Language Tools shared and isolating mutable data per computer.

### Windows downloads

| Architecture | EXE installer | MSI installer | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [Download EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-Setup-1.0.2-x64.exe) | [Download MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x64.msi) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x64-portable.zip) |
| x86 | [Download EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-Setup-1.0.2-x86.exe) | [Download MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86.msi) | [Download ZIP](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86-portable.zip) |

> **Windows installer note:** The EXE installer is recommended for most users. MSI packages may require Administrator permission depending on Windows or organization policy. Use the portable ZIP when installation is not practical.

### Linux downloads

| Package | Download |
| --- | --- |
| Debian / Ubuntu x86_64 | [OpenMind-Studio-1.0.2-amd64.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-amd64.deb) |
| AppImage x86_64 | [OpenMind-Studio-1.0.2-x86_64.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86_64.AppImage) |
| Portable x86_64 | [OpenMind-Studio-1.0.2-linux-x86_64-portable.tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-linux-x86_64-portable.tar.gz) |

For Linux, the AppImage is the recommended portable package.

See [RELEASE.md](RELEASE.md) for v1.0.2 changes and [RELEASE-REPORT.md](RELEASE-REPORT.md) for the artifact matrix and verification information.

---

## What's new in v1.0.2

### Multi-computer portable mode

OpenMind Studio now supports:

- **Only for me**
- **All users / Multi-computer — Recommended** for portable drives, labs, universities, offices, schools, and shared PCs

In Multi-computer mode:

- each computer receives its own isolated application profile
- the same physical computer returns to the same profile
- different computers receive different profiles
- changing the portable-drive letter does not create a new profile
- computer renaming does not change the profile
- cloned lab PCs are protected from sharing one profile when valid hardware identity signals differ

### Shared Runtime Manager and Language Tools

Large development tools remain shared across computers using the same OpenMind Studio drive.

Install once and reuse across connected computers:

- Node.js
- Python
- Go
- Rust
- PHP
- MariaDB binaries
- Git
- Fortran
- Pascal
- Assembly tools
- language servers
- formatters
- linters
- debuggers
- Language Tools packages

A runtime installed on PC-A can be detected and used on PC-B without downloading another copy.

### Per-computer mutable state

The following are isolated per computer where applicable:

- main SQLite database
- WebView2 profile
- AI conversation history
- search indexes
- application logs
- temporary state
- broker/runtime state
- LSP state
- MariaDB databases and runtime configuration
- phpMyAdmin machine-specific configuration

MariaDB **program files are shared**, while each computer keeps separate database data and runtime state.

### Safer migration and recovery

v1.0.2 improves SQLite migration and recovery with:

- SQLite-native backup for legacy profile migration
- read-only migration source handling
- integrity verification before promotion
- crash-safe temporary migration files
- concurrent-startup protection
- protection against repeatedly importing legacy data
- recovery handling for incomplete or corrupt migration state

---

## Designed for restricted PCs

OpenMind Studio is especially useful on:

- university computers and computer labs
- office PCs and shared Windows systems
- training centers
- systems without administrator rights
- machines where global PATH changes are restricted
- portable or temporary development workstations

OpenMind Studio prefers app-local runtimes and tools and avoids modifying the User or Machine `PATH` for normal workflows.

It does not intentionally bypass operating-system, firewall, proxy, authentication, administrator, or institutional security controls.

---

## Core features

- Monaco-based multi-file editor
- file explorer, tabs, breadcrumbs, search, Problems, Output and Debug Console
- integrated terminal
- Run Code workflows
- Runtime Manager
- Language Tools and LSP integration
- formatting and linting
- Git/source-control integration
- PHP + MariaDB + phpMyAdmin development stack
- image, PDF, DOCX, XLSX, CSV, Markdown, HTML and LaTeX previews
- workspace/project detection
- extension platform foundation
- optional AI providers
- updater/signature infrastructure
- portable runtime/tool resolution without global PATH mutation

Supported language/tooling areas include JavaScript, TypeScript, Python, PHP, C, C++, Java, Rust, Go, Fortran, Pascal, Assembly, HTML, CSS, JSON, YAML, SQL and related project types where the required runtime/tool is available.

---

## Runtime Manager

Runtime Manager downloads, installs, detects, repairs and resolves portable development runtimes inside the OpenMind Studio environment.

The important v1.0.2 behavior is:

```text
Runtime / Language Tool installed once
        ↓
stored in the shared OpenMind Studio installation
        ↓
available to every computer using that drive
```

Machine-specific caches or execution state do not redefine whether the shared runtime actually exists.

---

## PHP and MariaDB

OpenMind Studio includes a portable PHP development workflow with:

- PHP 8.x runtime support
- Composer
- PHP built-in server
- MariaDB
- phpMyAdmin
- local server controls
- port management
- Laravel-oriented workflows

In Multi-computer mode:

```text
MariaDB binaries     → shared
MariaDB database data → per computer
phpMyAdmin runtime   → shared
phpMyAdmin config    → per computer
```

This prevents one computer from overwriting another computer's database state while avoiding duplicate MariaDB installations.

---

## Privacy and security

OpenMind Studio is local-first.

Key principles:

- no global runtime installation required for normal portable workflows
- no User/Machine PATH mutation for app-managed tools
- per-computer mutable profiles in Multi-computer mode
- raw machine identifiers are not used as profile directory names
- no hidden AI request at launch
- no automatic project upload
- API keys are not intentionally written to logs
- database passwords are masked by default
- updater artifacts are signature verified
- package hashes are verified where supported
- the internal download gateway binds to localhost only

Windows uses DPAPI-backed protection for supported stored secrets. Linux security/storage capabilities may differ depending on the package and host environment.

---

## Storage note for Multi-computer mode

Typical measured profile usage is approximately:

- **15–25 MB per computer** for normal application state
- around **160 MB per computer** after MariaDB/MySQL data has been initialized

For deployments across hundreds or thousands of computers, plan portable-drive capacity accordingly. Old machine profiles are not automatically removed.

---

## Installation

Download the current packages from the [OpenMind Studio v1.0.2 release](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.2).

### Windows

- **EXE:** recommended for most users
- **MSI:** useful for Windows Installer / managed deployment; Administrator permission may be required
- **Portable ZIP:** extract and run without a normal installer

### Linux

- **DEB:** for compatible Debian/Ubuntu-style systems
- **AppImage:** recommended portable Linux package
- **Portable tar.gz:** extract and run on a compatible Linux host

---

## System requirements

Recommended baseline:

- Windows 10/11 or a compatible modern Linux distribution
- x64 recommended
- Windows x86 package available for supported 32-bit environments
- 4 GB RAM minimum
- 8 GB RAM or more recommended
- enough storage for selected runtimes and workloads
- Windows: WebView2 runtime available
- Linux: compatible GTK/WebKitGTK and related dependencies where required
- internet access for runtime/tool downloads when not using already-installed shared tools

---

## Release verification

Published release artifacts use the project's release signing and checksum workflow.

Check [RELEASE-REPORT.md](RELEASE-REPORT.md) and the release assets for:

- SHA-256 checksums
- detached updater/release signatures where provided
- Windows Authenticode signing status
- artifact names and package formats

Private signing material and passwords are never published in this repository.

---

## Repository policy

This repository is the **public distribution and release repository** for OpenMind Studio.

It contains release-facing documentation and published release assets through GitHub Releases. The private development source repository and private signing material are **not published here**.

Do not commit:

- signing private keys or passwords
- certificates containing private keys
- API secrets
- local databases
- machine profiles
- WebView data
- logs or test artifacts

---

## Previous release

The previous stable release was **v1.0.1**.

Its historical release information remains available through GitHub Releases. v1.0.2 supersedes it for new downloads.

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

See [LICENSE](LICENSE) for the complete license text.
