# OpenMind Studio v1.0.4 — Release Artifact Report

**Published:** 21 October 2026  
**Release:** [v1.0.4](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4)  
**Platforms:** Windows x64/x86, Linux x64/x86  
**Code signing:** Windows packages unsigned; Linux packages not GPG-signed  
**Automatic updates:** Unavailable for this build; updater signature/feed not generated

This report lists the 12 installable packages published with v1.0.4. The asset names, sizes and SHA-256 values are matched against GitHub's published asset metadata and the supplied v1.0.4 checksum manifest. These integrity hashes are **not** code signatures.

## Published packages

| Package | Format | Size (MB) | SHA-256 |
| --- | --- | ---: | --- |
| `OpenMind-Studio_1.0.4_linux_x64_portable.tar.gz` | Portable archive | 23.9 | `9bf384232e148802881880b7f1649b2d784584e3a560be149bac2d78463e9e0e` |
| `OpenMind-Studio_1.0.4_linux_x64.AppImage` | AppImage | 124.8 | `c2c31c14b5629e80820805eaa944c99c239ee960a8c65b4a19fc7538bfeb3f95` |
| `OpenMind-Studio_1.0.4_linux_x64.deb` | DEB | 24.4 | `08402ce3922c211d71928056adee4b093bcd7e65dee3cbbf853afed5c1d70ddb` |
| `OpenMind-Studio_1.0.4_linux_x86_portable.tar.gz` | Portable archive | 23.7 | `e152499b11f3cf71174597a70b1a25ba3fec33f211705f83c335b5f0e50c0031` |
| `OpenMind-Studio_1.0.4_linux_x86.AppImage` | AppImage | 120.5 | `39a286f2a7b5058c3c328aeb2671edc2d35ecc356e79edc527b631c46538e448` |
| `OpenMind-Studio_1.0.4_linux_x86.deb` | DEB | 24.1 | `3f73754725f8327aee5803d14896bf38ea74bd15614fc467537f16f4617d916d` |
| `OpenMind-Studio_1.0.4_windows_x64_portable.zip` | Portable ZIP | 195.6 | `08b08e19b98b91d15f6fcd0f46cb026784d7da8da96d143a11a39d7910484795` |
| `OpenMind-Studio_1.0.4_windows_x64_setup.exe` | Setup EXE | 176.1 | `ecfe5193b6f941011f21c3584279fef596e551e78e5ed54a26f5388cc0fadceb` |
| `OpenMind-Studio_1.0.4_windows_x64.msi` | MSI | 196.4 | `de9b45c4a5acdf7f959a6aca554f4cd97f983f2d61bb06844495a89dbb0d7e98` |
| `OpenMind-Studio_1.0.4_windows_x86_portable.zip` | Portable ZIP | 194.5 | `286f43d386dcb83a77d0b78856c1c2adb809d6800f1911cd3af29044c7c3e2d7` |
| `OpenMind-Studio_1.0.4_windows_x86_setup.exe` | Setup EXE | 175.7 | `473a0a4e178b1ea67464881b88ba1be47df6354a5c6c579f8f0753c76e878871` |
| `OpenMind-Studio_1.0.4_windows_x86.msi` | MSI | 195.3 | `c8933796c87b2784d3a8282697f1deaee9a26a3abb1b30d3d4c339670c6cc36c` |

[Download all packages](https://github.com/smshagor-dev/OpenMind-Studio/releases/tag/v1.0.4) · [Checksums](SHA256SUMS.txt)

Additional launch scripts are included on GitHub Releases: `Start.OpenMind.Studio.bat` (Windows), `openmind-studio.sh` (Linux), and `Start.OpenMind.Studio.command` (macOS). The macOS script **is not a macOS application package**.

## Release verification status

- All 12 published package checksums match the supplied checksum manifest and GitHub release asset metadata.
- The supplied Windows build report records a build on **21 October 2026, 08:13 UTC**, and explicitly reports no configured Windows code-signing certificate.
- The Windows build report states no updater signatures were produced, so no signed automatic update feed was generated.
- The supplied release notes also identify Linux packages as not GPG-signed.
- Physical multi-computer and classroom acceptance tests remain pending.
- macOS release binaries were not built for v1.0.4.
- These records do **not** establish end-user installation success, runtime feature verification, independent checksum recomputation from downloaded binaries, or trusted code-signing.

## Distribution and upgrade

Prefer x64 on compatible systems. Select Setup EXE/MSI for installed Windows use, Portable ZIP for removable/shared media, DEB/AppImage for appropriate Linux systems, or the Linux portable archive.

Download v1.0.4 manually. Back up work before upgrading; for shared installations, close OpenMind Studio on all clients and update the existing network installation from one computer. Do not distribute these packages as Authenticode- or GPG-signed.

Historical release reports are retained in Git history. For the full list of changes see [v1.0.4 release notes](RELEASE.md).
