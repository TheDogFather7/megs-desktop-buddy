# Security policy

## Supported versions

| Version | Supported |
|---|---|
| 1.0.2 | Yes |
| 1.0.1 | No. Please update: 1.0.2 moves to a newer Electron and picks up its upstream security fixes. |
| 1.0.0 | No. Please update: 1.0.1 and later include security fixes. |

## Reporting a vulnerability

Please **don't** open a public issue for security problems.

Report it privately instead: go to this repository's **Security** tab and choose **Report a vulnerability**, or open [the private report form](../../security/advisories/new) directly. Include the Megs version, steps to reproduce, and what an attacker could achieve.

You should get a reply within 7 days. Please give us a reasonable time to ship a fix before you disclose the issue publicly.

## Known limitations of 1.0.2

These are already known, so you don't need to report them:

- **Not code-signed.** The installer, the app and the uninstaller have no Authenticode signature. Always check the SHA-256 of the installer against the one in the release notes before you run it.
- **Updates aren't automatic.** Megs checks GitHub once a day and tells you when a new version is out, but you download and install it yourself. Megs 1.0.0 doesn't check at all, so watch this repository's releases.
- **Bundled runtime.** 1.0.2 ships Electron 45.2.3 (Chromium 156, Node.js 24.22). Electron 45 gets security fixes until 27 April 2027, and we plan to move Megs to a newer Electron before then.

## Verifying a download

In PowerShell, from the folder you saved the installer to:

```powershell
(Get-FileHash .\Megs-Setup-1.0.2.exe -Algorithm SHA256).Hash -eq '19b7af7ead2a004f39ccd3d34fad46aa834ffec69f39b2522c9351101d1f3e81'
```

It must print **True**. The hash is also on the [release page](../../releases/tag/v1.0.2). If you'd rather compare by eye, `Get-FileHash .\Megs-Setup-1.0.2.exe` prints it in capital letters, which is fine.
