# OpenMind Studio v1.0.5 — Release Notes

**Released:** October 27, 2026 · **Previous:** v1.0.4 · **Available builds:** Windows x64, Linux x64

[Download v1.0.5](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.5) · [Available packages](README.md#downloads)

OpenMind Studio v1.0.5 improves VS Code extension compatibility, editor recovery, OpenMind AI Cloud settings, and Windows Pascal development. Highlights are grounded in merged source commits after v1.0.4; they do not imply all third-party extensions or supported environments have passed end-to-end testing.

## New and improved

### VS Code extension compatibility
- Expanded VS Code settings, profiles, and extension import, including running imported extensions.
- Added native ESM extension support, inline completions, and native dialog APIs.
- Expanded Monaco extension interfaces for decorations, snippets, selections, editor focus, columns, indentation, line numbers, undo/EOL behavior, and edit validation.
- Added more language APIs for semantic tokens, inlay hints, colors, language configurations, and lifecycle events.
- Added extension workspace-folder quick picking, task pseudoterminals, debugger source documents, and notebook interactions.
- Improved extension terminal and window-focus events and save participants.

### Editor and document recovery
- Added named and unnamed untitled documents with native Save As support.
- Added writable provider-backed virtual documents and read-only editor mutation guards.
- Improved recovery of unsaved local files and virtual/provider-backed buffers.
- Isolated recovery records across windows and improved extra-window restoration.
- Flushed editor buffers before Quit and updates; improved protection when on-disk content conflicts.

### OpenMind AI Cloud
- Redesigned OpenMind AI Cloud provider settings.
- Removed desktop-side text and generation caps in supported input flows. Actual context, output, and rate limits still depend on the chosen model/provider.

### Pascal tooling
- Added PascalABC.NET as an optional Windows compiler alongside Free Pascal, with Runtime Manager integration, compiler selection, offline packaging, Run Code, and error diagnostics.
- Improved extraction of ZIP filenames encoded with DOS Cyrillic code page 866.

## Fixed
- Extension activation race conditions and filesystem permission escape cases.
- Truncated extension-store implementation and related tests.
- Native extension-host channel allowlist handling.
- Document provider ownership on failed registration.
- Stale snippet insertions and extension decoration placement in Monaco editors.
- Debugger transport cleanup and document identity handling during Save As.
- Conflicts affecting unsaved local file recovery and multi-window sessions.
- Extension language-configuration lifecycle cleanup.

## Packages published

- **Windows x64:** NSIS setup EXE, MSI, portable ZIP.
- **Linux x64:** DEB, AppImage, portable tar.gz.
- **Windows/Linux x86 and macOS installers:** not uploaded for this release.

Use only links from the [official v1.0.5 release](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.5).

## Known limitations and security

- Not all VS Code extension APIs are supported. Compatibility varies by extension.
- PascalABC.NET is Windows-only and does not include its own language server or debugger.
- Linux builds require compatible GTK/WebKitGTK and glibc.
- Desktop AI input changes cannot bypass provider-side or model context limits.
- No standalone v1.0.5 updater signature or `latest.json` asset is currently attached to the release; do not rely on automatic installation of this version.
- Operating-system publisher signing (such as Windows Authenticode) is independent of updater signing and must be checked on the binaries.

## Upgrading

1. Save changes and close the editor.
2. Download the correct v1.0.5 package.
3. Upgrade your existing install or replace only portable program files while preserving user data.
4. Restart and verify workspace settings, extensions, and unsaved-recovery behavior.

**Previous release:** [v1.0.4 release notes](RELEASE-v1.0.4.md).
