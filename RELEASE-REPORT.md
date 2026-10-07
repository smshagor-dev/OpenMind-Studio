# OpenMind Studio 1.0.1 — release artifacts

- Version: **1.0.1**
- Channel: **Stable**
- Platforms: **Windows, Linux**
- Architectures: **x64, x86**
- Windows build type: **test-signed**
- Windows signer: **CN=OpenMind**
- Timestamp: **DigiCert** (`http://timestamp.digicert.com`)
- Release: [v1.0.1](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.1)

## Published assets

| File | Platform | Kind | Size | SHA-256 |
| --- | --- | --- | ---: | --- |
| OpenMind-Studio-Setup-x64.exe | Windows x64 | EXE installer | 237.1 MiB | `f52764928a25d44276176e5bf0f90b3fe4d934892cc0154e6f245c4cd5592c03` |
| OpenMind-Studio-x64.msi | Windows x64 | MSI installer | 253.7 MiB | `e7666172464921e399e0d7b32a82769b03891af4731a5a94b46ed9db7b00a16c` |
| OpenMind-Studio-Portable-x64.zip | Windows x64 | Portable ZIP | 252.9 MiB | `154f4b1baaa262144d4c05e2e484dfb78614b10040545011fec4c485e434ade5` |
| OpenMind-Studio-Setup-x86.exe | Windows x86 | EXE installer | 236.7 MiB | `61262c942ec95b00236972ab9890891e22cb52ec665834a9432dfec5ee0d1bb5` |
| OpenMind-Studio-x86.msi | Windows x86 | MSI installer | 253.1 MiB | `c409ba0c319a07e26b4a99b940fca3940abc9562dbda55f47db5e3e310be4aac` |
| OpenMind-Studio-Portable-x86.zip | Windows x86 | Portable ZIP | 252.2 MiB | `62798e0c16ab149bf6e8e859c81bd18839ee8e36b16703f45859b4e6de5201aa` |
| OpenMind-Studio-x64.deb | Linux x64 | DEB | 15.7 MiB | `43af2d656ca12112b308e307bb9094cf2ad53bc88dfdd6c490f98ea62bdb096b` |
| OpenMind-Studio-x64.AppImage | Linux x64 | AppImage | 91.1 MiB | `ee00e44e24a9ea7e6074acc5a46ff2c55b619c20c9eff74e7b72cd8b8f910a5f` |
| OpenMind-Studio-Portable-linux-x64.zip | Linux x64 | Portable ZIP | 15.4 MiB | `7fba0b0a8281804da420c2f76d686b51762aee2bcec021515ce3345387a37255` |
| OpenMind-Studio-x86.deb | Linux x86 | DEB | 15.7 MiB | `4f1bb299ea45f08eb8cb83f1ee79ffe0d6113c623dee891dcb7dd1cd91cd17bd` |
| OpenMind-Studio-x86.AppImage | Linux x86 | AppImage | 108.2 MiB | `eaefae7901833e19b403d09e82380638da876d7b15a13ec85bdcd3f7b14dfdb4` |
| OpenMind-Studio-Portable-linux-x86.zip | Linux x86 | Portable ZIP | 15.4 MiB | `af1791f59e5af2ba19fdaa9ada1830031010e41e5544193555a3d73541ba1d14` |

## Signing notes

The Windows v1.0.1 build is **Authenticode test-signed** with the self-signed `CN=OpenMind` certificate and a DigiCert timestamp. The EXE/MSI installers are signed, and the portable ZIP packages contain signed `OpenMindStudio.exe` payloads. Tauri updater `.sig` files remain valid after signing.

Because the certificate is self-signed, computers that do not explicitly trust `CN=OpenMind` may still show SmartScreen or publisher-trust warnings. This is a signed test release, not publicly trusted production code signing.
