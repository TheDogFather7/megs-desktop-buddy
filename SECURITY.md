# Security policy

## Supported versions

| Version | Supported |
|---|---|
| 1.0.x | Yes |

## Reporting a vulnerability

Please **don't** open a public issue for security problems.

Report it privately instead: go to this repository's **Security** tab and choose **Report a vulnerability**, or open [the private report form](../../security/advisories/new) directly. Include the Megs version, steps to reproduce, and what an attacker could achieve.

You should get a reply within 7 days. Please give us a reasonable time to ship a fix before you disclose the issue publicly.

## Known limitations of 1.0.0

These are already known, so you don't need to report them:

- **Not code-signed.** The installer, the app and the uninstaller have no Authenticode signature. Always check the SHA-256 of the installer against the one in the release notes before you run it.
- **No automatic updates.** Megs never checks for new versions. Watch this repository's releases to hear about fixes.
- **Bundled runtime.** 1.0.0 ships Electron 44.4.5 (Chromium 152, Node.js 24.21). Newer Electron 44.x releases exist; a future Megs release will move to a current Electron.

## Verifying a download

In PowerShell, from the folder you saved the installer to:

```powershell
Get-FileHash .\Megs-Setup-1.0.0.exe -Algorithm SHA256
```

The hash must match the one published on the [release page](../../releases/tag/v1.0.0). PowerShell prints it in capital letters, which is fine. [INSTALL.md](INSTALL.md#2-check-the-download) has a one-line command that prints **True** or **False**.
