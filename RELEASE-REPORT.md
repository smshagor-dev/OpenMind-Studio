# OpenMind Studio v1.0.0 — Release Report

**Release:** v1.0.0  
**Channel:** Stable  
**Platform:** Windows 10 / 11  
**Architectures:** x64 and x86  
**Published:** 2026-09-30  
**Distribution:** GitHub Releases

OpenMind Studio v1.0.0 is the first stable production release focused on portable development for university labs, office computers, shared Windows systems, and other restricted PCs where administrator access or system-wide developer tooling may not be available.

## Release downloads

| File | Architecture | Type | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| `OpenMind.Studio_x64.exe` | x64 | NSIS EXE installer | 196.75 MiB | `9e3db0a3785f61a006f6d764662b5c2af5a66b34c0198a5634c9dea19a0cc24c` |
| `OpenMind.Studio_x64_en-US.msi` | x64 | MSI installer | 212.87 MiB | `ab8f03054e3aee096208378b36c88ee83c2111ec71cf16842f7e73cb9d728cc1` |
| `OpenMind.Studio_x86.exe` | x86 | NSIS EXE installer | 196.36 MiB | `d13c4d48bf0486c8e99856564b51d0fc6a4ee7f8fbf31dcf5b004038ee1f5233` |
| `OpenMind.Studio_x86_en-US.msi` | x86 | MSI installer | 212.25 MiB | `2b2d1e5e6eb85cc15e4df798be81ed8777c8cb2573cbb49292affaded4288031` |

## Direct downloads

- [x64 EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x64.exe)
- [x64 MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x64_en-US.msi)
- [x86 EXE](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x86.exe)
- [x86 MSI](https://github.com/smshagor-dev/OpenMind-Studio/releases/download/v1.0.0/OpenMind.Studio_x86_en-US.msi)

Full release page: https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.0

## Major production areas

- Monaco-based editor and workspace
- Explorer, tabs, breadcrumbs, themes, profiles and icon themes
- Integrated terminal
- Run Code workflow
- Runtime Manager
- Portable Node.js, npm and pnpm
- Portable Python and pip
- Portable Git and Source Control integration
- PHP 8.x runtime support
- Composer
- MariaDB and phpMyAdmin local stack
- Go/toolchain integration where configured
- Language Server Protocol foundation
- Formatter/linter/tool discovery
- Workspace search and project detection
- File previews for images, PDF, DOCX, XLSX, CSV, Markdown, HTML and related formats
- Local VSIX extension foundation
- Optional Claude, OpenAI/OpenAI-compatible, Gemini and local AI-provider architecture
- Proxy-aware download broker
- Localhost-only package/download gateway
- Resume, cancellation and progress-aware downloads
- SHA-256/package integrity verification
- Application updater infrastructure with signature verification
- NSIS EXE and MSI packaging
- x64 and x86 release targets

## Restricted-PC design

OpenMind Studio is designed to prefer application-local runtimes and tools instead of depending on global installations. Normal app-managed workflows avoid changing the User or Machine `PATH` and are intended to remain practical on university and office PCs with limited permissions.

The application does not intentionally bypass administrator restrictions, authentication, firewall rules, proxies, or institutional security policies.

## Release policy

Compiled `.exe` and `.msi` files are published as GitHub Release assets and are not stored directly in the `main` source branch.

Private signing keys, passwords, certificates, API secrets and other credentials must never be committed to the repository.
