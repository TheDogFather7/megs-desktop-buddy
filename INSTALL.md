# Installing Megs on Windows 11

Version 1.0.2 · about 5 minutes · no admin rights needed

## 1. Download

From the [v1.0.2 release](../../releases/tag/v1.0.2), download **`Megs-Setup-1.0.2.exe`** (<<SIZE-1.0.2>> MB).

Already have Megs 1.0.0 or 1.0.1? Follow the same steps: the installer upgrades it in place and keeps your settings, chat history and keys.

## 2. Check the download

This confirms the file is exactly the one published here. Open **Terminal** in your Downloads folder (right-click an empty spot in File Explorer → **Open in Terminal**) and run:

```powershell
(Get-FileHash .\Megs-Setup-1.0.2.exe -Algorithm SHA256).Hash -eq '<<SHA256-1.0.2>>'
```

It must print **True**. If it prints **False**, delete the file and download it again. **Don't run an installer whose hash doesn't match.**

To see the hash itself, run `Get-FileHash .\Megs-Setup-1.0.2.exe`. PowerShell prints it in capital letters, which is fine: the comparison above ignores case.

## 3. Run the installer

Double-click `Megs-Setup-1.0.2.exe`. It installs for your Windows account only, so there's no admin prompt. It adds Megs to the Start menu and your desktop, and starts Megs when it finishes.

### "Windows protected your PC"

Megs isn't code-signed, so SmartScreen shows this warning. If the hash in step 2 matched, click **More info**, then **Run anyway**.

### "Smart App Control blocked…"

Smart App Control blocks every unsigned app, including Megs itself, and there's no way to allow just one app. **Megs can't run while Smart App Control is on.** Turning Smart App Control off lowers protection for every app on your PC, so we don't recommend doing that just for Megs.

### Microsoft Defender removed the installer

Don't restore it from quarantine. Download it again from the release page and check the hash. If Defender flags a file whose hash matches, please [open an issue](../../issues) so we can report the false positive to Microsoft.

## 4. Give Megs a brain

Megs appears in the bottom-right corner and opens its sign-in window. Pick where it gets its answers:

- **OpenRouter (easiest):** click **Sign in with OpenRouter**, log in in your browser, and approve Megs. One account gives you Claude, GPT, Gemini and more.
- **Claude, OpenAI or Gemini:** paste an API key from your provider's console and click **Connect**.
- **Ollama, LM Studio and others:** pick the provider, enter the server address and click **Connect**. If the server needs an API key, Megs sends it only to that server, and over plain `http://` only to this computer or your home network (an address like `192.168.x.x` or `name.local`). Anywhere else, use the server's `https://` address.

Megs checks the key by listing your models, then stores it encrypted with Windows' built-in data protection. See [PRIVACY.md](PRIVACY.md) for what Megs sends and stores.

## 5. Say hi

| Action | What it does |
|---|---|
| Click Megs | Open or close the chat |
| Drag Megs | Move it anywhere on screen |
| Right-click Megs | Menu: new chat, hide, snooze, sass level, settings, quit |
| Ctrl + Alt + Space | Open or close the chat from any app |
| Esc | Close the chat |
| Shift + Enter | New line in a message |

- **Keep the tray icon visible:** Windows 11 hides new tray icons behind the **^** arrow. Go to **Settings → Personalization → Taskbar → Other system tray icons** and turn on Megs.
- **Start with Windows:** right-click Megs → **Settings… → Behavior → Start Megs when I log in**.
- **Too much sass?** Right-click Megs → **Snooze the sass**, or pick a calmer level under **Settings… → Personality**.

## Updating

Once a day, Megs asks GitHub whether a newer version is out. If there is one, Megs tells you once in a speech bubble, and **Settings… → About** shows it until you update. Megs never downloads or installs anything by itself.

To update, download the new installer from the [releases page](../../releases/latest), check its hash as in step 2 (each release lists its own), and run it. It installs over the old version and keeps your settings, chat history and keys.

To stop the daily check, turn off **Settings… → Behavior → Check for new versions**. Megs 1.0.0 doesn't check at all, so to hear about releases from it, use **Watch → Custom → Releases** on this repository.

## Uninstalling

1. Open **Settings → Apps → Installed apps**, find Megs, click **⋯** and choose **Uninstall**.
2. The uninstaller removes Megs, its "Start Megs when I log in" entry, its cached copy of the installer, and `%APPDATA%\Megs` (your settings, chat history and saved keys).
3. If you signed in with OpenRouter, also delete the "Megs desktop buddy" key in your OpenRouter account.

**Uninstalling 1.0.0?** Its uninstaller leaves things behind. Turn off **Start Megs when I log in** first (**Settings… → Behavior**), and afterwards delete `%APPDATA%\Megs` and `%LOCALAPPDATA%\megs-desktop-buddy-updater` yourself. Or update to the latest version first, then uninstall.

## Troubleshooting

| Problem | What to do |
|---|---|
| Megs isn't on screen | Click the Megs tray icon (behind **^**) and choose **Show Megs**, or open **Settings… → Behavior → Bring Megs back to the corner**. |
| Ctrl + Alt + Space does nothing | Another app already uses it. Choose a different shortcut in **Settings… → Behavior → Chat shortcut**. |
| "My brain rejected that key." | Paste the key again in **Settings… → Brain** and check that your account has credits. |
| "Your saved key is for …, so Megs didn't send it here." | You changed the server address. Megs only sends a saved key to the server it was saved for, so paste the key for the new server. |
