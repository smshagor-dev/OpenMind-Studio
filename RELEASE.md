# OpenMind Studio v1.0.3 — current stable release

**Published:** October 13, 2026  
**Previous:** v1.0.2  
**Platforms:** Windows x64/x86; Linux x64/x86  
**Download:** https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.3

This document tracks the **published** release, not an internal development build. The canonical published changelog is on the release page.

# OpenMind Studio v1.0.3

**Release date:** October 13, 2026  
**Previous version:** v1.0.2  
**Release highlights:** Collaborative Workspace Preview, Built-in Browser, Automatic Updates, Smarter Installation, and Multi-PC Reliability

OpenMind Studio v1.0.3 brings a substantial set of new capabilities to the portable desktop development environment. This release introduces an early collaborative editing experience, an integrated browser for frontend development, an automatic update system, and major improvements to Windows installation, shared network deployments, and reliability.

## ✨ New Features

### Collaborative Workspace (Preview)

- **Room-based collaboration:** Share a project folder from the owner's computer and invite others to join using a Room Code, without an OpenMind account.
- **Real-time collaborative editing:** Work on shared text documents with collaborative cursors, selections, presence, and document synchronization.
- **Participant management:** Owner-controlled membership, roles, permissions, moderation, and an auditable history of collaboration actions.
- **Local-first recovery:** Accepted edits are persisted before acknowledgement, with recovery and conflict-handling safeguards designed to protect work after interruptions.
- **Flexible connectivity:** Local-network discovery and support for configured signaling, STUN, and TURN services for connections across networks.
- **Voice collaboration infrastructure:** Peer-to-peer voice sessions and an optional classroom-oriented media-server mode.
- **Security-focused sharing:** Authenticated participants, protected Room Codes, restricted shared paths, and authorization checks on remote operations.

> **Preview notice:** Collaboration has passed automated and same-machine testing, but real two-computer LAN, cross-network, microphone/audio, and classroom validation is still pending. It should be treated as a preview, not as a fully verified production classroom solution.

### Built-in Browser and Live Web Preview

- Run `.html` and `.htm` files directly in the editor's **Browser** panel, alongside the Output view.
- Preview local HTML, CSS, JavaScript, images, ES modules, and local `fetch` requests through a loopback-only development server.
- Inspect console output, JavaScript errors, rejected promises, and failed resource loads without leaving OpenMind Studio.
- Automatically reload the active preview when supported project files change on disk or are saved in the editor.
- Compile SCSS/Sass for previews, with compilation errors displayed directly in the page.
- Run a JavaScript file in the browser when Node.js is unavailable; keep the existing Node.js execution path when Node.js is installed.
- Use built-in Reload and Open in Your Browser actions.

### Automatic and Verified Updates

- Check for stable releases from GitHub automatically, with a manual **Help → Check for Updates** action.
- Show update availability and details from the status bar and update dialog.
- Download eligible updates and verify their release signatures before installation.
- Install supported Windows updates when closing the application or using **Restart to Update**.
- Protect unsaved editor content and warn before interrupting active terminals or running programs.
- Update portable Windows installations by replacing application files while preserving user data, settings, and runtimes.
- Allow managed/shared installations to report new versions without modifying a shared deployment automatically.
- Add an **Automatic Updates** preference to control automatic downloading; update availability checks can still occur when downloading is disabled.

### Smarter Installation and Deployment

- Add **For Me** and **Recommended for All Users** choices to the Windows setup experience.
- Introduce an explicitly managed shared-network installation layout, with shared application/tool files and separate per-computer, per-user data.
- Detect existing Windows installations and offer **Update** or **Repair** instead of presenting first-install questions again.
- Add support for maintaining desktop shortcuts for network/lab deployments, including an administrator deployment script.
- Improve MSI deployments so standard users keep their application data in writable, user-specific locations.

### Expanded Release Packaging

- Prepare Windows **x64 and x86** packages as NSIS Setup (`.exe`), MSI (`.msi`), and Portable ZIP (`.zip`).
- Prepare Linux **x64 and x86** packages as DEB (`.deb`), AppImage, and Portable TAR.GZ archives.
- Generate architecture-specific release names, SHA-256 checksums, updater signatures, and `latest.json` update metadata.
- Introduce reproducible release collection and verification checks for Windows and Linux artifacts.

## 🚀 Improvements

### Editor and Development Workflow

- Preserve the built-in browser's current page state when switching between Browser and Output tabs.
- Avoid duplicate browser reloads when a file is saved just before running a preview.
- Report HTML browser support more accurately in Project & Language Status.
- Improve the experience of opening a saved file when no workspace folder is currently open.

### Multi-PC and Portable Operation

- Separate machine-specific databases, settings, logs, browser profiles, temporary data, and tool caches from shared network installations.
- Preserve an existing Data Scope selection instead of repeatedly asking users to configure the same installation.
- Resolve mapped drives, UNC shares, and equivalent installation paths more consistently, preventing accidental duplicate local profiles.
- Preserve existing profiles and settings when upgrading eligible installations.
- Improve the recovery path when Data Scope metadata is missing, damaged, or temporarily inaccessible.
- Keep shared runtime installations consistent across several computers through cross-process locking and safer installation handoff.
- Isolate development tool caches for shared deployments, including package managers and language toolchains.

### Installation and Update Safety

- Perform in-place upgrades without the earlier uninstall-first flow that could alter installation layout or hide existing data.
- Detect applications and install files that are still in use before replacing them.
- Prevent simultaneous setup processes from modifying the same installation.
- Reject accidental downgrades by default and avoid replacing MSI installations with an incompatible per-user setup.
- Add signed-update verification, checksum checks, installation locking, and rollback safeguards for portable application-file replacement.
- Add clearer update behavior for Linux: Linux builds can detect available versions, but **do not perform automatic self-replacement**.

### Security, Compliance, and Release Quality

- Include a Windows application manifest for normal-user execution, supported Windows versions, and long-path handling.
- Improve error classification and actionable messages for installation, database, and shared-runtime failures.
- Add third-party license notices to release packages and strengthen dependency-license verification.
- Add/update project documentation for privacy, security reporting, contributions, community conduct, deployment, and release signing.
- Expand CI checks and release verification for Rust, TypeScript, frontend builds, artifacts, update metadata, and platform architecture.
- Prepare integration with SignPath Foundation signing; trusted Windows code signing must still be completed separately.

## 🐛 Bug Fixes

### Installation and Startup

- Fixed newer installers treating an existing installation as a fresh installation.
- Fixed the previous setup flow that could uninstall an older version before updating and expose users to a different data location.
- Fixed shared installations not being detected when originally installed by a different Windows user.
- Fixed a case where an MSI installation could be replaced by a per-user installation.
- Fixed unintended downgrades through the newer installer workflow.
- Fixed startup failures for standard users running MSI installations from protected locations.
- Fixed cases where a temporary Data Scope read failure brought back the first-run setup screen.
- Fixed misleading startup messages that labeled unrelated profile failures as database corruption.

### Multi-PC Data Protection

- Fixed a network installation opening the same SQLite database from multiple computers when the layout was inferred incorrectly.
- Added a session guard that detects another computer using the same database and refuses the conflicting start rather than risking concurrent access.
- Fixed duplicate local profiles caused by launching the same network installation through different path aliases.
- Fixed shared-runtime reconciliation deleting another computer's incomplete installation or disturbing an active runtime.
- Fixed language-server extraction conflicts when multiple computers prepared the same server at the same time.
- Fixed shared runtime permission failures displaying only a low-level lock-file error instead of explaining missing write access.
- Fixed incorrect shared-cache placement for several development toolchains and package managers.

### Browser, Networking, and Updates

- Fixed preview state being lost when navigating away from the Browser panel to Output.
- Fixed an unnecessary duplicate browser reload in the save-and-run flow.
- Fixed an unhandled error when the Network view could not subscribe to download progress.
- Fixed the missing end-to-end update-check wiring and the absent release-feed generation that had prevented the updater from being usable.
- Fixed a Linux update-selection risk that could otherwise have attempted to use a Windows portable archive.

### Collaboration and Testing

- Fixed collaboration recovery paths that could overwrite accepted edits after an owner crash or reconnect.
- Improved protection against stale document snapshots replacing newer shared content.
- Fixed test-side Windows installation-record pollution and a flaky test involving transient SQLite WAL files.

## 🔜 Upcoming: OpenMindAI Coding Agent

We are working toward bringing the **OpenMindAI Coding Agent** into OpenMind Studio as a more integrated coding companion.

Planned capabilities include:

- **Context-aware coding assistance:** Get help understanding and working with code in the active project.
- **Explain, fix, and refactor:** Ask the agent to explain code, investigate errors, and suggest improvements.
- **Agent-assisted edits:** Review proposed code changes before applying them to project files.
- **Local AI integration:** Explore support for compatible locally running OpenMindAI models, with an emphasis on privacy and user control.

> **Coming in a future update:** The OpenMindAI Coding Agent is on the roadmap and is **not included in v1.0.3**. Features and availability may change during development.

## ⚠️ Upgrade and Compatibility Notes

- **One-time manual update:** OpenMind Studio v1.0.2 and earlier do not have this release's automatic update path. Download and install v1.0.3 manually once.
- **Back up before upgrading:** v1.0.3 introduces collaboration database migrations. A database opened by v1.0.3 cannot be reopened directly by v1.0.2. Keep a pre-upgrade backup if you may need to roll back.
- **Keep your installation type:** Update existing installations in place. For shared installations, close the application on all participating computers before upgrading the shared program files.
- **Linux updates:** Linux builds notify users when a newer release exists but do not automatically replace their application files.
- **32-bit Windows:** Some bundled offline language tooling is x64-only and may require separate installation on 32-bit systems.
- **Collaboration preview:** Real-hardware multi-PC and cross-network validation remains outstanding. Local collaboration data is not a replacement for regular project backups.
- **Code signing:** Updater `.sig` files and SHA-256 checksums are not the same as Windows Authenticode signatures. Verify the published artifacts and trusted signing status before distributing them as signed builds.

---

**OpenMind Studio** — A portable-first desktop development environment built with Rust, Tauri, React, TypeScript, and Monaco Editor.

**Changes since:** v1.0.2


---

## Upcoming v1.0.4 — not published

Prepared improvements focus on local-network deployment discovery and explicit trust, verification of deployment packages, per-user shared-install Desktop shortcuts, improvements to runtime/language-tools locking and mapped-drive profiles, cache isolation and safer network package serving.

Physical multi-PC university-network validation is still pending; Windows packages are not trusted Authenticode-signed. Do not advertise a v1.0.4 GitHub release before it is actually published.

### AI Coding Agent status

Configurable AI chat/provider integration exists in the development architecture, but an autonomous AI Coding Agent (multi-file workspace edits, tool execution, approval controls and durable/resumable tasks) is **not confirmed as a delivered feature** of v1.0.3 or v1.0.4. This is upcoming development, not part of the verified v1.0.4 release highlights.

## Historical releases

[v1.0.2](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.2) · [v1.0.1](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1)
