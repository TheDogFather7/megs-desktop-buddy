# Privacy

Megs has no server of its own. It collects no analytics, telemetry or crash reports, and it doesn't check for updates. The only network traffic is between your computer and the AI provider you choose.

## What is sent to your AI provider

Megs sends requests to the provider you pick in **Settings → Brain**, under your own account and subject to that provider's privacy policy. Depending on your choice, that's one of:

- `openrouter.ai`, `api.anthropic.com`, `api.openai.com` or `generativelanguage.googleapis.com`
- another OpenAI-compatible service you select or enter (for example Groq, Mistral, DeepSeek, xAI or Together)
- a local server such as Ollama (`http://localhost:11434`) or LM Studio. Traffic stays on your computer unless you change the server address to another machine.

### When you chat

Each request includes:

- the conversation so far (up to the last 40 messages / 60,000 characters), including earlier messages restored from history after a restart
- a system prompt containing the name you gave in **Settings → Personality** ("What should Megs call you?"), your **Custom instructions**, your local date and time, and your operating system name
- anything you paste into the chat, including clipboard text you insert with the paste button

### When Megs makes a remark on its own

Under **Settings → Personality → Where the sass comes from**:

| Setting | What is sent |
|---|---|
| **Built-in lines only** | Nothing. Remarks come from a list built into the app. |
| **Mix** (the default) | Now and then (at most once every 5 minutes), Megs asks your AI to write a remark without you doing anything. |
| **AI-written** | Same as Mix, but for every idle remark (still at most once every 5 minutes). |

These background requests include the same system prompt as a chat (name, custom instructions, local time), a short description of the situation (for example how many minutes you've been away or busy, or that it's late at night), and **the first 100 characters of your most recent chat message**. The reply may show up in Megs's speech bubble on screen.

Choose **Built-in lines only** if you don't want this.

## What is stored on your computer

Everything lives in `%APPDATA%\Megs`:

| File | Contents | Protection |
|---|---|---|
| `secrets.json` | Your API keys | Encrypted with Windows DPAPI (tied to your Windows account). If encryption isn't available, keys are stored base64-encoded, which is **not** encryption, and the Brain tab warns you. |
| `chat-history.json` | The last 60 chat messages | Plain text. Turn off **Settings → Behavior → Remember the current chat between restarts** to stop saving it, or use **Clear chat history**. |
| `settings.json` | Your preferences, including your name and custom instructions | Plain text |

Uninstalling Megs doesn't delete this folder. Delete `%APPDATA%\Megs` yourself to remove everything.

## Signing in with OpenRouter

**Sign in with OpenRouter** opens your browser and creates an API key on your OpenRouter account labelled "Megs desktop buddy". Signing out in Megs only deletes the key from your computer. To revoke the key itself, delete it in your OpenRouter account's key settings.
