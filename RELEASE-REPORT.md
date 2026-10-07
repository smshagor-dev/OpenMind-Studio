# OpenMind Studio 1.0.1 — release artifacts

- Version: 1.0.1
- Architecture: x64, x86
- Build type: **test-signed**
- Windows signer: **CN=OpenMind**
- Timestamp: **DigiCert** (`http://timestamp.digicert.com`)
- Built: 2026-10-07T11:59:52.122Z

| File | Kind | Size | SHA256 |
| --- | --- | --- | --- |
| OpenMind-Studio-Setup-1.0.1-x64.exe | setup | 237.1 MB | `f52764928a25d44276176e5bf0f90b3fe4d934892cc0154e6f245c4cd5592c03` |
| OpenMind-Studio-1.0.1-x64.msi | msi | 253.7 MB | `e7666172464921e399e0d7b32a82769b03891af4731a5a94b46ed9db7b00a16c` |
| OpenMind-Studio-Setup-1.0.1-x86.exe | setup | 236.7 MB | `61262c942ec95b00236972ab9890891e22cb52ec665834a9432dfec5ee0d1bb5` |
| OpenMind-Studio-1.0.1-x86.msi | msi | 253.1 MB | `c409ba0c319a07e26b4a99b940fca3940abc9562dbda55f47db5e3e310be4aac` |
| OpenMind-Studio-Portable-1.0.1-x64.zip | portable | 252.9 MB | `154f4b1baaa262144d4c05e2e484dfb78614b10040545011fec4c485e434ade5` |
| OpenMind-Studio-Portable-1.0.1-x86.zip | portable | 252.2 MB | `62798e0c16ab149bf6e8e859c81bd18839ee8e36b16703f45859b4e6de5201aa` |

The Windows v1.0.1 build is **test-signed** with the self-signed `CN=OpenMind` certificate and a DigiCert timestamp. The EXE/MSI installers are Authenticode-signed, and the portable ZIP packages contain signed application executables. Tauri updater `.sig` files were regenerated from the signed installers and verified successfully.

Because the certificate is self-signed, computers that do not explicitly trust `CN=OpenMind` can still show SmartScreen or publisher-trust warnings. This is a signed test release, not publicly trusted production code signing.

Signing: {"mode":"test-signed","message":"Signing with a TEST certificate from the Windows certificate store: the build is marked TEST-SIGNED (not trusted by other computers).","timestamp":"http://timestamp.digicert.com"}
