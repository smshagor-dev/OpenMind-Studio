# OpenMind Studio

**OpenMind Studio** is a portable desktop IDE for Windows, built for students, developers, and restricted lab/university PCs where global installs and administrator access are often not available.

It is not a web app. It is a native desktop application built with **Rust, Tauri 2, React, TypeScript, and Monaco Editor**. The goal is simple: open a project, edit code, run commands, manage local runtimes, preview files, search a workspace, and work with Git without depending on a globally configured development machine.

---

## Current release

**Version:** `0.1.0`  
**Status:** first stable public/test release base  
**License:** Apache License 2.0 (`Apache-2.0`)  
**Build type:** unsigned Windows builds

Available artifacts in this repository:

| Artifact | Architecture | Purpose |
| --- | --- | --- |
| `OpenMind-Studio-Setup-0.1.0-x64.exe` | x64 | Recommended installer for 64-bit Windows |
| `OpenMind-Studio-0.1.0-x64.msi` | x64 | MSI package for 64-bit Windows |
| `OpenMind-Studio-Setup-0.1.0-x86.exe` | x86 | Installer for 32-bit Windows |
| `OpenMind-Studio-0.1.0-x86.msi` | x86 | MSI package for 32-bit Windows |
| `SHA256SUMS.txt` | all | Checksums for release files |
| `RELEASE-REPORT.md` | all | Release artifact report |

> The installers are currently **not code-signed**. Windows SmartScreen may show a warning until a production signing certificate is used.

---

## Why use OpenMind Studio?

Use OpenMind Studio when you need a development environment that is:

- **Portable** — designed to run from its own app folder.
- **Student/lab friendly** — useful on PCs where admin rights are limited.
- **Runtime aware** — manages portable tools such as Node.js, Python, PHP, Git, Composer, MariaDB, and phpMyAdmin.
- **Project focused** — detects common web, backend, desktop, mobile, scripting, systems, Docker, database, and config projects.
- **Offline friendly** — core app features do not require an account or cloud service.
- **Safe by default** — no User/Machine `PATH` mutation, no hidden runtime installs, no hidden AI requests.

OpenMind Studio is especially useful for:

- HTML/CSS/JavaScript/TypeScript projects
- React/Vite/Next.js-style web apps
- Python scripts and backend apps
- PHP/Laravel projects with local MariaDB/phpMyAdmin
- Rust, Go, Docker, SQL, Markdown, JSON/YAML/TOML projects
- mixed-language university or training projects

---

## What is included

### Editor and workspace

- Monaco-based code editor
- Tabs and split editor workflow
- File explorer
- Workspace session restore
- Recent files and folders
- Search, symbols, and reference search foundation
- VS Code-like application menus
- Keyboard shortcuts and settings UI
- Profiles and icon themes

### Formatting and code quality

- Format Document support
- Format on Save support
- Built-in JSON/package.json formatting
- Formatter/tool discovery for common stacks
- Clear missing-formatter messages when a formatter is not available

### Terminal and runtime management

- Integrated terminal
- Portable runtime manager
- Portable runtime/tool preference before system fallback
- App-local environment injection for launched terminals/processes
- No global `PATH` change

Supported runtime/tool areas include:

- Node.js
- Python
- PHP
- Git
- Composer
- MariaDB
- phpMyAdmin
- language tools and toolchain manifests

### Git and source control

- Source Control view
- Portable Git support
- Git resolver that prefers OpenMind-managed Git when available
- No need to modify system Git configuration just to use the editor

### PHP local stack

OpenMind Studio includes a professional local PHP stack workflow:

- PHP server control panel
- MariaDB start/stop/restart support
- phpMyAdmin integration
- Composer tools
- Laravel helper area
- Database credentials shown safely with masked password, reveal, and copy actions
- No automatic `.env` rewrite without user action

### Preview system

Read-only previews are available for common project files:

- Images: PNG, JPG/JPEG, WebP, GIF, BMP, SVG
- PDF
- DOCX
- XLSX
- CSV
- Markdown
- HTML
- LaTeX source
- Binary/unsupported files show safe messages instead of loading incorrectly

### AI provider architecture

OpenMind Studio has an optional AI provider system:

- Claude provider path
- OpenAI/OpenAI-compatible provider path
- Gemini provider path
- local loopback OpenAI-compatible provider path
- encrypted API key storage
- no AI panel unless at least one provider is configured/enabled
- no hidden AI request at launch
- online providers ask before sending content

AI is optional. The base editor works without AI.

### Extensions

OpenMind Studio includes an extension foundation:

- local VSIX install
- extension enable/disable/uninstall
- commands, keybindings, menus, languages, snippets, themes
- activity bar views and tree views
- status bar items
- secure WebviewPanel support
- permission guard

Full VS Code extension compatibility is still a long-term goal. Some APIs such as WebviewView, Terminal API, Task API, Notebook API, and full Debug extension API are not complete yet.

---

## Language Server Protocol support

The project includes LSP foundation and support for core editor intelligence. Current built-in/core areas include:

- TypeScript / JavaScript
- JSON
- HTML
- CSS
- PHP/Python where configured through available tools

Some additional language servers may be detected but not fully startable until bundled/offline LSP packs are completed.

Planned next-stage work includes a larger offline LSP bundle so common language servers can be shipped app-local without runtime downloads.

---

## Install and run

### Recommended: setup installer

Download the matching installer for your Windows architecture:

- 64-bit Windows: `OpenMind-Studio-Setup-0.1.0-x64.exe`
- 32-bit Windows: `OpenMind-Studio-Setup-0.1.0-x86.exe`

The installer shows the Apache License 2.0 agreement. You must accept the license before installation continues.

### MSI packages

Use MSI when you specifically need MSI-based installation:

- `OpenMind-Studio-0.1.0-x64.msi`
- `OpenMind-Studio-0.1.0-x86.msi`

MSI installation may require administrator approval depending on Windows policy.

### Verify downloads

Use `SHA256SUMS.txt` to verify downloaded files.

Example with PowerShell:

```powershell
Get-FileHash .\OpenMind-Studio-Setup-0.1.0-x64.exe -Algorithm SHA256
```

Compare the output with `SHA256SUMS.txt`.

---

## Privacy and safety model

OpenMind Studio is designed around local-first development.

- No hidden AI requests
- No hidden marketplace fetch at app launch
- No User/Machine `PATH` mutation
- No global runtime install
- No admin requirement for normal app operation
- API keys are not shown in logs
- DB passwords are masked by default
- Extension permissions are guarded
- Online actions happen only after user action

Some Windows WebView2 background connections may appear because WebView2 is a Microsoft runtime component.

---

## What OpenMind Studio is not

OpenMind Studio is **not** trying to be a cloud IDE or a browser-only editor.

It is also not yet:

- full VS Code API parity
- a full mobile emulator/device manager
- a full notebook editor
- a signed production Windows release
- an auto-updating app
- a cloud sync product

Those areas are part of the longer roadmap.

---

## Development setup

Prerequisites:

- Rust toolchain
- Node.js
- pnpm

Install frontend dependencies:

```sh
pnpm install
```

Run in development mode:

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

## Packaging

Typical packaging commands:

```sh
pnpm package:installer
pnpm package:portable
```

Release artifacts should include:

- setup EXE
- MSI
- SHA256 checksums
- release report

Signing is optional and environment-driven. Do not commit certificates or signing passwords.

---

## Project structure

```text
crates/       Rust domain crates
src-tauri/    Tauri desktop shell and backend command layer
src/          React + TypeScript frontend
scripts/      build, packaging, and tooling scripts
docs/         release, sync, toolchain, and development documentation
```

---

## Roadmap highlights

Completed major areas include:

- editor/workspace foundation
- integrated terminal
- runtime manager
- Git/source control
- LSP/DAP foundation
- PHP/MariaDB/phpMyAdmin stack
- extension system v1
- file preview system
- indexed search
- AI provider architecture
- language/project detection
- toolchain pack system
- application menu and About window
- formatting system
- profiles, icon themes, startup/release prep

Planned future milestones include:

- offline bundled LSP pack
- Extension System v2 / stronger VS Code compatibility
- advanced debug/tasks/notebook support
- system-language localization
- proxy-aware terminal/network resilience
- Visual Studio-style optional workload installer

---

## Author

**Md Shahanur Islam Shagor**  
Founder & Developer, OpenMind Studio  
Independent Researcher and Software Engineer

Support: `smshagor.dev@gmail.com`  
GitHub: `smshagor-dev`  
Telegram: `@smshagor1`  
WhatsApp: `smshagor1`

---

## License

OpenMind Studio is released under the **Apache License 2.0**.

See [`LICENSE`](LICENSE).
