# OpenMind Studio v1.0.2

**Channel:** Stable  
**Platforms:** Windows and Linux  
**Windows architectures:** x64 and x86  
**Linux architecture:** x86_64 / amd64  
**License:** Apache-2.0

OpenMind Studio v1.0.2 focuses on safer multi-computer portability, shared Runtime Manager and Language Tools installations, machine-specific mutable state, stronger SQLite migration/recovery, and more reliable release packaging.

## Downloads

### Windows

| Architecture | EXE installer | MSI installer | Portable ZIP |
| --- | --- | --- | --- |
| x64 | [OpenMind-Studio-Setup-1.0.2-x64.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-Setup-1.0.2-x64.exe) | [OpenMind-Studio-1.0.2-x64.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x64.msi) | [OpenMind-Studio-1.0.2-x64-portable.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x64-portable.zip) |
| x86 | [OpenMind-Studio-Setup-1.0.2-x86.exe](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-Setup-1.0.2-x86.exe) | [OpenMind-Studio-1.0.2-x86.msi](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86.msi) | [OpenMind-Studio-1.0.2-x86-portable.zip](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86-portable.zip) |

**Recommended:** use the EXE installer for most Windows systems. MSI may require Administrator permission depending on Windows or organization policy. Use the portable ZIP when normal installation is not practical.

### Linux

| Package | Download |
| --- | --- |
| DEB x86_64 / amd64 | [OpenMind-Studio-1.0.2-amd64.deb](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-amd64.deb) |
| AppImage x86_64 | [OpenMind-Studio-1.0.2-x86_64.AppImage](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-x86_64.AppImage) |
| Portable x86_64 | [OpenMind-Studio-1.0.2-linux-x86_64-portable.tar.gz](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.2/OpenMind-Studio-1.0.2-linux-x86_64-portable.tar.gz) |

For Linux, AppImage is the recommended portable package.

## v1.0.1 → v1.0.2

### New

- **All users / Multi-computer mode**, recommended for portable drives, university labs, schools, offices, shared PCs, and multi-machine workflows.
- **Per-computer profiles** for mutable application data while keeping the portable application and development toolchain shared.
- **Stable machine identity resolution** designed to distinguish cloned lab PCs without using the computer name or portable-drive path as identity.
- **Machine-profile collision protection** using derived identity metadata.
- **Safe legacy database migration** using SQLite-native backup and integrity validation.
- **Interrupted-migration recovery** for temporary migration databases and incomplete migration state.
- **OS-backed coordination/locking** for profile initialization and migration.
- **Machine-specific WebView2, AI history, search-index, logs, temp and runtime state**.
- **Per-computer MariaDB data/configuration** while MariaDB program files stay shared.
- **Per-computer phpMyAdmin configuration** through a shared safe runtime loader.

### Updated

- Runtime Manager now treats the **shared portable runtime installation** as authoritative rather than relying only on machine-specific database records.
- A runtime installed once can be detected and used by every computer using the same OpenMind Studio drive.
- Language Tools follow the same shared-installation model.
- Runtime detection and execution continue to work after portable drive-letter changes.
- Scope switching between personal and Multi-computer mode no longer requires runtime or Language Tool reinstallation.
- MariaDB binaries remain shared while mutable database state is isolated per computer.
- Run Code build state, asm-lsp configuration, extension-host logs, broker/update temp state and related mutable paths are isolated where required.
- SQLite startup ordering now resolves the correct data scope/profile before the production database is opened.
- Release packaging names are standardized for v1.0.2 Windows and Linux artifacts.
- Linux portable packaging now uses `.tar.gz` for the x86_64 portable artifact.

### Fixed

- Multiple computers accidentally sharing one OpenMind Studio SQLite database.
- Cloned PCs potentially resolving to the same machine profile when one identifier was duplicated.
- Computer-name changes affecting profile identity.
- Portable drive paths or drive letters influencing machine identity.
- Runtime installation status appearing missing on another computer even though the runtime already existed on the shared drive.
- Language Tools requiring unnecessary redownload/reinstallation on another computer.
- Windows migration failures caused by flushing copied files through a read-only handle.
- Legacy AI-history validation opening the source database read-write.
- Unsafe assumptions around WAL-mode database copying.
- Repeated legacy imports after a valid machine database already existed.
- Incomplete migration state being promoted incorrectly.
- Profile initialization and migration race conditions during concurrent launch.
- phpMyAdmin machine-specific secrets, ports and profile paths being written into the shared runtime folder.
- MariaDB mutable state conflicts across different computers.
- Shared Run Code, LSP, log and temporary state that should have been machine-specific.
- Portable runtime detection problems after moving the application to a different drive letter.

## Multi-computer behavior

The intended v1.0.2 model is:

```text
Shared across computers:
- OpenMind Studio application
- Runtime Manager downloads
- Node.js / Python / Go / Rust / PHP
- MariaDB binaries
- Git
- Fortran / Pascal / Assembly tools
- language servers
- formatters / linters / debuggers
- Language Tools packages

Per computer:
- SQLite application database
- WebView2 profile
- AI conversations
- search index
- logs
- cache / temp / process state
- MariaDB databases and runtime state
- phpMyAdmin machine configuration
```

A runtime or Language Tool installed on one computer should be available to another computer using the same OpenMind Studio drive without a second download.

## Migration and recovery

v1.0.2 protects existing single-profile data during migration.

The migration path uses a SQLite-native snapshot into a temporary `.migrating` database, validates it with SQLite integrity checks, and promotes it only after verification.

Key recovery rules:

- a valid existing machine database always wins over legacy data
- a missing migration marker never triggers a second import
- a valid `.migrating` database can only be promoted when no final database exists
- a corrupt final database is never silently overwritten
- legacy source databases remain preserved
- migration/recovery mutations occur under an OS-backed lock and re-check state after the lock is acquired

## Validation

The v1.0.2 codebase passed:

- Rust: **1,454 passed, 0 failed, 21 ignored**
- Frontend: **2,113 passed**
- TypeScript build/typecheck: passed
- ESLint: passed
- Rust formatting: passed
- Clippy with warnings treated as errors: passed
- Production frontend build: passed
- Multi-PC portable simulation: passed

The simulation covered cloned-machine identity separation, shared runtimes, shared Language Tools, MariaDB isolation, WebView/AI/search isolation, data-scope switching, profile restoration, and portable drive-letter relocation.

## Storage planning

Measured per-computer mutable profile usage is approximately:

- **15–25 MB** for normal application state
- around **160 MB** after MariaDB/MySQL data has been initialized

For very large deployments, plan portable-drive capacity accordingly. Old machine profiles are not automatically cleaned up.

## Platform notes

### Windows

Windows remains the primary full portable/offline-tooling edition.

v1.0.2 provides:

- x64 EXE installer
- x64 MSI installer
- x64 portable ZIP
- x86 EXE installer
- x86 MSI installer
- x86 portable ZIP

Windows MSI installation may require Administrator permission depending on policy.

### Linux

v1.0.2 publishes x86_64 / amd64 packages:

- DEB
- AppImage
- portable `.tar.gz`

Linux relies on compatible host GTK/WebKit and related system dependencies where required.

## Verification

Final published artifact sizes, SHA-256 hashes and signing verification are recorded in [RELEASE-REPORT.md](RELEASE-REPORT.md) and the v1.0.2 GitHub Release assets.

Release page: https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.2

## Previous release

Historical v1.0.1 release information remains available in GitHub Releases. v1.0.2 supersedes v1.0.1 for new downloads.
