# OpenMind Studio 1.0.2 — release artifacts

- Version: **1.0.2**
- Channel: **Stable**
- Platforms: **Windows, Linux**
- Windows architectures: **x64, x86**
- Linux architecture: **x86_64 / amd64**
- License: **Apache-2.0**
- Release: [v1.0.2](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.2)

## Expected published assets

### Windows

| File | Platform | Kind | Verification |
| --- | --- | --- | --- |
| `OpenMind-Studio-Setup-1.0.2-x64.exe` | Windows x64 | EXE installer | Authenticode + release signature + SHA-256 |
| `OpenMind-Studio-1.0.2-x64.msi` | Windows x64 | MSI installer | Authenticode + release signature + SHA-256 |
| `OpenMind-Studio-1.0.2-x64-portable.zip` | Windows x64 | Portable ZIP | detached signature + SHA-256 |
| `OpenMind-Studio-Setup-1.0.2-x86.exe` | Windows x86 | EXE installer | Authenticode + release signature + SHA-256 |
| `OpenMind-Studio-1.0.2-x86.msi` | Windows x86 | MSI installer | Authenticode + release signature + SHA-256 |
| `OpenMind-Studio-1.0.2-x86-portable.zip` | Windows x86 | Portable ZIP | detached signature + SHA-256 |

### Linux

| File | Platform | Kind | Verification |
| --- | --- | --- | --- |
| `OpenMind-Studio-1.0.2-amd64.deb` | Linux x86_64 | DEB | detached signature + SHA-256 |
| `OpenMind-Studio-1.0.2-x86_64.AppImage` | Linux x86_64 | AppImage | detached signature + SHA-256 |
| `OpenMind-Studio-1.0.2-linux-x86_64-portable.tar.gz` | Linux x86_64 | Portable archive | detached signature + SHA-256 |

### Verification files

The v1.0.2 release also publishes the supported detached `.sig` files plus:

- `SHA256SUMS.txt`
- `SHA256SUMS.txt.sig`

Exact artifact sizes and SHA-256 values are generated from the **final signed release files** during publication and must match the GitHub Release assets.

## Validation status

The v1.0.2 codebase passed the required pre-release validation:

| Check | Result |
| --- | --- |
| Rust formatting | PASS |
| Rust clippy, warnings denied | PASS |
| Rust workspace tests | **1,454 passed, 0 failed, 21 ignored** |
| TypeScript typecheck | PASS |
| ESLint | PASS |
| Frontend tests | **2,113 passed** across 187 files |
| Production frontend build | PASS |
| Multi-PC portable simulation | PASS |

## Multi-computer validation

The v1.0.2 simulation verified:

- different computers receive different machine profiles
- cloned lab PCs with the same MachineGuid can still be separated by valid hardware identity
- reconnecting the same computer restores the same profile
- drive-letter and portable-folder relocation do not require runtime reinstallation
- Runtime Manager installations remain shared across computers
- Language Tools remain shared across computers
- Node, Python and PHP execute from the shared portable installation on another profile
- MariaDB binaries remain shared while database data is isolated
- WebView2, AI history, search indexes, logs and temporary state are isolated
- switching data scope does not reinstall runtimes
- legacy database migration preserves the original source database
- raw machine identifiers are not stored in profile names or release-facing state

## Data architecture

### Shared across computers

- OpenMind Studio application
- Runtime Manager downloads and installed runtimes
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

### Isolated per computer

- application SQLite database
- WebView2 data
- AI conversation history
- search index
- logs
- temporary/process state
- broker and runtime mutable state
- MariaDB databases and machine-specific configuration
- phpMyAdmin machine-specific configuration

## Storage planning

Measured mutable profile usage:

- approximately **15–25 MB per computer** for normal application state
- approximately **160 MB per computer** after MariaDB/MySQL has been initialized

For 1,000 computers, deployments should plan for roughly **20 GB** of normal profile data, potentially up to around **160 GB** if MariaDB is initialized on every profile.

Old machine profiles are not automatically removed.

## Signing notes

Windows EXE/MSI artifacts are expected to be Authenticode-signed and timestamped according to the project's release-signing workflow.

Portable and Linux artifacts use the project's supported detached signature workflow.

Updater/release signatures are separate from Windows Authenticode signatures.

Private signing keys and passwords must never be committed or published.

## Publication rule

Do not consider v1.0.2 fully published until:

1. every expected artifact exists;
2. every required signature has been generated and verified;
3. `SHA256SUMS.txt` is generated from the final signed artifacts;
4. release smoke tests pass for the environments that can be physically tested;
5. the GitHub v1.0.2 release contains the final artifact set without duplicate names.

Historical v1.0.1 release assets remain available separately.
