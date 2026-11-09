# Installing Megs on Windows 11

Version 1.0.0 · about 5 minutes · no admin rights needed

## 1. Download

From the [v1.0.0 release](../../releases/tag/v1.0.0), download **`Megs-Setup-1.0.0.exe`** (105 MB).

## 2. Check the download

This confirms the file is exactly the one published here. Open **Terminal** in your Downloads folder (right-click an empty spot in File Explorer → **Open in Terminal**) and run:

```powershell
Get-FileHash .\Megs-Setup-1.0.0.exe -Algorithm SHA256
```

The hash must be exactly:

```
e0392aab9e02c0d55e128161a3cbeb8a982dac41dd132f728609f950c584958a
```

If it doesn't match, delete the file and download it again. **Don't run an installer whose hash doesn't match.**

## 3. Run the installer

Double-click `Megs-Setup-1.0.0.exe`. It installs for your Windows account only, so there's no admin prompt. It adds Megs to the Start menu and your desktop, and starts Megs when it finishes.

### "Windows protected your PC"

Megs 1.0.0 isn't code-signed, so SmartScreen shows this warning. If the hash in step 2 matched, click **More info**, then **Run anyway**.

### "Smart App Control blocked…"

Smart App Control blocks every unsigned app, including Megs itself, and there's no way to allow just one app. **Megs 1.0.0 can't run while Smart App Control is on.** Turning Smart App Control off lowers protection for every app on your PC, so we don't recommend doing that just for Megs.

### Microsoft Defender removed the installer

Don't restore it from quarantine. Download it again from the release page and check the hash. If Defender flags a file whose hash matches, please [open an issue](../../issues) so we can report the false positive to Microsoft.

## 4. Give Megs a brain

Megs appears in the bottom-right corner and opens its sign-in window. Pick where it gets its answers:

- **OpenRouter (easiest):** click **Sign in with OpenRouter**, log in in your browser, and approve Megs. One account gives you Claude, GPT, Gemini and more.
- **Claude, OpenAI or Gemini:** paste an API key from your provider's console and click **Connect**.
- **Ollama, LM Studio and others:** pick the provider, enter the server address and click **Connect**.

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

## Uninstalling

1. If you turned on **Start Megs when I log in**, turn it off first (**Settings… → Behavior**). The 1.0.0 uninstaller doesn't remove that startup entry.
2. Open **Settings → Apps → Installed apps**, find Megs, click **⋯** and choose **Uninstall**.
3. The uninstaller leaves these behind. Delete them if you want everything gone:
   - `%APPDATA%\Megs`: your settings, chat history and saved (encrypted) API keys
   - `%LOCALAPPDATA%\megs-desktop-buddy-updater`: a copy of the installer (about 105 MB)
4. If you signed in with OpenRouter, also delete the "Megs desktop buddy" key in your OpenRouter account.

## Troubleshooting

| Problem | What to do |
|---|---|
| Megs isn't on screen | Click the Megs tray icon (behind **^**) and choose **Show Megs**, or open **Settings… → Behavior → Bring Megs back to the corner**. |
| Ctrl + Alt + Space does nothing | Another app already uses it. Choose a different shortcut in **Settings… → Behavior → Chat shortcut**. |
| "My brain rejected that key." | Paste the key again in **Settings… → Brain** and check that your account has credits. |
