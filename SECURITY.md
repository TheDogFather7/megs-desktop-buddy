# Security policy

## Supported versions

| Version | Supported |
|---|---|
| 1.0.1 | Yes |
| 1.0.0 | No. Please update: 1.0.1 includes security fixes. |

## Reporting a vulnerability

Please **don't** open a public issue for security problems.

Report it privately instead: go to this repository's **Security** tab and choose **Report a vulnerability**, or open [the private report form](../../security/advisories/new) directly. Include the Megs version, steps to reproduce, and what an attacker could achieve.

You should get a reply within 7 days. Please give us a reasonable time to ship a fix before you disclose the issue publicly.

## Known limitations of 1.0.1

These are already known, so you don't need to report them:

- **Not code-signed.** The installer, the app and the uninstaller have no Authenticode signature. Always check the SHA-256 of the installer against the one in the release notes before you run it.
- **Updates aren't automatic.** Megs checks GitHub once a day and tells you when a new version is out, but you download and install it yourself. Megs 1.0.0 doesn't check at all, so watch this repository's releases.
- **Bundled runtime.** 1.0.1 ships Electron 44.10.2 (Chromium 152, Node.js 24.22). Electron 44 gets security fixes until 2 March 2027; a later Megs release will move to a newer Electron before then.

## Verifying a download

In PowerShell, from the folder you saved the installer to:

```powershell
(Get-FileHash .\Megs-Setup-1.0.1.exe -Algorithm SHA256).Hash -eq 'TODO-SHA256-SETUP-1.0.1'
```

It must print **True**. The hash is also on the [release page](../../releases/tag/v1.0.1). If you'd rather compare by eye, `Get-FileHash .\Megs-Setup-1.0.1.exe` prints it in capital letters, which is fine.
