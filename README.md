# megs-desktop-buddy

**Megs** is a sassy floppy-disk desktop buddy for Windows 11, powered by the LLM of your choice. It sits in the corner of your screen, makes the occasional remark, and opens a chat when you click it.

You bring your own model: sign in with OpenRouter, paste an Anthropic, OpenAI or Gemini API key, or point it at a local server such as Ollama or LM Studio.

## Download

Get **`Megs-Setup-1.0.0.exe`** from the [v1.0.0 release](../../releases/tag/v1.0.0), then follow [INSTALL.md](INSTALL.md).

SHA-256 of the installer:

```
e0392aab9e02c0d55e128161a3cbeb8a982dac41dd132f728609f950c584958a  Megs-Setup-1.0.0.exe
```

**Requirements:** Windows 11 (64-bit) and an account with an LLM provider, or a local model server.

> [!IMPORTANT]
> The 1.0.0 installer and app are **not code-signed**, so Windows SmartScreen will warn you, and Smart App Control will block Megs completely. Read [INSTALL.md](INSTALL.md) before you run it.

## Privacy at a glance

- No analytics, telemetry, crash reporting or update checks. Megs only talks to the provider you choose.
- Your messages, plus your display name, local time and custom instructions, go to that provider under your own account.
- With the default **Mix** setting, Megs occasionally asks your AI for an idle remark on its own, which includes how long you've been idle and the start of your last message. Choose **Built-in lines only** to turn that off.
- API keys are encrypted with Windows DPAPI. Chat history is stored on your computer in plain text.

Full details: [PRIVACY.md](PRIVACY.md).

## Security

Please report vulnerabilities privately. See [SECURITY.md](SECURITY.md).

## License

Megs is released under the [MIT License](LICENSE). The app bundles third-party software under its own licenses: see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
