# Privacy

Megs has no server of its own. It collects no analytics, telemetry or crash reports. Its network traffic is between your computer and the AI provider you choose, plus a daily check with GitHub for a newer version of Megs (see [Checking for new versions](#checking-for-new-versions)).

## What is sent to your AI provider

Megs sends requests to the provider you pick in **Settings… → Brain**, under your own account and subject to that provider's privacy policy. Depending on your choice, that's one of:

- `openrouter.ai`, `api.anthropic.com`, `api.openai.com` or `generativelanguage.googleapis.com`
- another OpenAI-compatible service you select or enter (for example Groq, Mistral, DeepSeek, xAI or Together). A key you save for such a server is only ever sent to that server, and over plain `http://` only to your own computer or home network.
- a local server such as Ollama (`http://localhost:11434`) or LM Studio. Traffic stays on your computer unless you change the server address to another machine.

### When you chat

Each request includes:

- the conversation so far (up to the last 40 messages / 60,000 characters), including earlier messages restored from history after a restart
- a system prompt containing the name you gave in **Settings… → Personality** ("What should Megs call you?"), your **Custom instructions**, your local date and time, and your operating system name
- anything you paste into the chat, including clipboard text you insert with the paste button

### When Megs makes a remark on its own

Under **Settings… → Personality → Where the sass comes from**:

| Setting | What is sent |
|---|---|
| **Built-in lines only** | Nothing. Remarks come from a list built into the app. |
| **Mix** (the default) | Now and then (at most once every 5 minutes), Megs asks your AI to write a remark without you doing anything. |
| **AI-written** | Same as Mix, but for every idle remark (still at most once every 5 minutes). |

These background requests include the same system prompt as a chat (name, custom instructions, local time), a short description of the situation (for example how many minutes you've been away or busy, or that it's late at night), and **the first 100 characters of your most recent chat message**. The reply may show up in Megs's speech bubble on screen.

Choose **Built-in lines only** if you don't want this.

## Checking for new versions

A minute after Megs starts, and then once a day while it runs, Megs asks GitHub's public releases API (`api.github.com`) for the latest release of this repository. The request carries no cookies, API keys or personal details, and identifies itself only as `Megs`. Like any web request, it shows GitHub your IP address. [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) applies.

Megs never downloads or installs anything by itself. If a newer version is out, it tells you once in a speech bubble and shows it under **Settings… → About**. **Get it** opens this repository's releases page in your browser.

To turn the check off, switch off **Settings… → Behavior → Check for new versions**.

## What is stored on your computer

Everything lives in `%APPDATA%\Megs`:

| File | Contents | Protection |
|---|---|---|
| `secrets.json` | Your API keys | Encrypted with Windows DPAPI (tied to your Windows account). If secure storage isn't available, Megs keeps keys in memory only, never on disk, and you sign in again each time it starts. The Brain tab tells you when that's the case. |
| `chat-history.json` | The last 60 chat messages | Plain text. Turn off **Settings… → Behavior → Remember the current chat between restarts** to stop saving it, or use **Clear chat history**. |
| `settings.json` | Your preferences, including your name and custom instructions, and the newest version the update check has seen | Plain text |

Uninstalling Megs 1.0.1 or later deletes this folder. The 1.0.0 uninstaller didn't, so if you uninstalled 1.0.0, delete `%APPDATA%\Megs` yourself.

## Signing in with OpenRouter

**Sign in with OpenRouter** opens your browser and creates an API key on your OpenRouter account labelled "Megs desktop buddy". Signing out in Megs only deletes the key from your computer. To revoke the key itself, delete it in your OpenRouter account's key settings.
