# OpenMind Studio 1.0.1 — release artifacts

- Version: **1.0.1**
- Channel: **Stable**
- Published: **2026-10-07**
- Platforms: **Windows, Linux**
- Architectures: **x64, x86**
- Windows Authenticode signing: **unsigned**
- Release source: [GitHub v1.0.1](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1)

## Published artifacts

| File | Platform | Kind | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| OpenMind-Studio-Setup-x64.exe | Windows x64 | EXE installer | 237.1 MiB | `7b1f68cc430d89a9a87c73c3c214a3991c8b1c7b9af4707f09b5835a53912a75` |
| OpenMind-Studio-x64.msi | Windows x64 | MSI installer | 253.7 MiB | `d334b42ed3710655ffd92d647431b681839c83ff76b6b3a9bbc101b4fca8bbf7` |
| OpenMind-Studio-Portable-x64.zip | Windows x64 | Portable ZIP | 252.9 MiB | `6b2eb72e69d0eb8e1597f1c90a119ea07edc57be029499289d62a717069bf2d2` |
| OpenMind-Studio-Setup-x86.exe | Windows x86 | EXE installer | 236.7 MiB | `099c3109337874affd53436c8ae1b3faae8eaf95f867956882e6a06ffb52121e` |
| OpenMind-Studio-x86.msi | Windows x86 | MSI installer | 253.1 MiB | `fbfedadaa23dc27d0357e71f53c72f5d29444814b66a6ccff8815a31687694f9` |
| OpenMind-Studio-Portable-x86.zip | Windows x86 | Portable ZIP | 252.2 MiB | `8f3f8952b7e78caa788791650e78dacdeade2edb882e429923dbed8f5d98cbf3` |
| OpenMind-Studio-x64.deb | Linux x64 | DEB | 15.7 MiB | `43af2d656ca12112b308e307bb9094cf2ad53bc88dfdd6c490f98ea62bdb096b` |
| OpenMind-Studio-x64.AppImage | Linux x64 | AppImage | 91.1 MiB | `ee00e44e24a9ea7e6074acc5a46ff2c55b619c20c9eff74e7b72cd8b8f910a5f` |
| OpenMind-Studio-Portable-linux-x64.zip | Linux x64 | Portable ZIP | 15.4 MiB | `7fba0b0a8281804da420c2f76d686b51762aee2bcec021515ce3345387a37255` |
| OpenMind-Studio-x86.deb | Linux x86 | DEB | 15.7 MiB | `4f1bb299ea45f08eb8cb83f1ee79ffe0d6113c623dee891dcb7dd1cd91cd17bd` |
| OpenMind-Studio-x86.AppImage | Linux x86 | AppImage | 108.2 MiB | `eaefae7901833e19b403d09e82380638da876d7b15a13ec85bdcd3f7b14dfdb4` |
| OpenMind-Studio-Portable-linux-x86.zip | Linux x86 | Portable ZIP | 15.4 MiB | `af1791f59e5af2ba19fdaa9ada1830031010e41e5544193555a3d73541ba1d14` |

## Notes

Windows EXE/MSI/portable packages are much larger because the Windows edition carries additional portable/offline tooling. Linux DEB and portable ZIP packages rely more heavily on compatible system libraries and omit the Windows-only offline LSP/formatter/Python bundles.

The Windows installers are not Authenticode code-signed, so Windows SmartScreen may display a warning. Tauri updater/package signatures are separate from Windows Authenticode signing.

For copy/paste verification, use [`SHA256SUMS.txt`](SHA256SUMS.txt).
