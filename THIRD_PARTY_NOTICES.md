# Third-party notices

The Megs installer and app include the following third-party software. Each is distributed under its own license; full license texts ship with the app in the install folder.

| Component | Version | License | License text in the install folder |
|---|---|---|---|
| [Electron](https://www.electronjs.org/) | 45.2.3 | MIT | `LICENSE.electron.txt` |
| [Chromium](https://www.chromium.org/) and its dependencies (bundled in Electron) | 156.0.8078.80 | BSD-3-Clause and others | `LICENSES.chromium.html` |
| [Node.js](https://nodejs.org/) (bundled in Electron) | 24.22.2 | MIT and others | `LICENSES.chromium.html` |
| [DOMPurify](https://github.com/cure53/DOMPurify) | 3.4.17 | MPL-2.0 OR Apache-2.0 | `resources\app.asar` → `node_modules/dompurify/LICENSE` and `LICENSE-MPL` |
| [marked](https://github.com/markedjs/marked) | 18.1.3 | MIT | `resources\app.asar` → `node_modules/marked/LICENSE` |
| [@types/trusted-types](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/trusted-types) (bundled with DOMPurify) | 2.0.7 | MIT | `resources\app.asar` → `node_modules/@types/trusted-types/LICENSE` |

The Windows installer and uninstaller are built with [electron-builder](https://www.electron.build/) (MIT) on [NSIS](https://nsis.sourceforge.io/) (zlib/libpng license), together with the NSIS plugins that electron-builder bundles, each under its own license.

This list is for Megs 1.0.2. Megs 1.0.1 shipped Electron 44.10.2 (Chromium 152.0.7977.169, Node.js 24.22.2) and marked 18.0.14. Megs 1.0.0 shipped Electron 44.4.5 (Chromium 152.0.7977.130, Node.js 24.21.0), DOMPurify 3.4.16 and marked 18.0.14, and its installer also included electron-builder's `elevate.exe` helper.
