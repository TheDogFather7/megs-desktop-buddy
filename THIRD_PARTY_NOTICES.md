# Third-party notices

The Megs installer and app include the following third-party software. Each is distributed under its own license; full license texts ship with the app in the install folder.

| Component | Version | License | License text in the install folder |
|---|---|---|---|
| [Electron](https://www.electronjs.org/) | 44.4.5 | MIT | `LICENSE.electron.txt` |
| [Chromium](https://www.chromium.org/) and its dependencies (bundled in Electron) | 152.0.7977.130 | BSD-3-Clause and others | `LICENSES.chromium.html` |
| [Node.js](https://nodejs.org/) (bundled in Electron) | 24.21.0 | MIT and others | `LICENSES.chromium.html` |
| [DOMPurify](https://github.com/cure53/DOMPurify) | 3.4.16 | MPL-2.0 OR Apache-2.0 | `resources\app.asar` → `node_modules/dompurify/LICENSE` and `LICENSE-MPL` |
| [marked](https://github.com/markedjs/marked) | 18.0.14 | MIT | `resources\app.asar` → `node_modules/marked/LICENSE` |

The Windows installer and uninstaller are built with [electron-builder](https://www.electron.build/) (MIT) on [NSIS](https://nsis.sourceforge.io/) (zlib/libpng license), together with the NSIS plugins and the `elevate.exe` helper that electron-builder bundles, each under its own license.
