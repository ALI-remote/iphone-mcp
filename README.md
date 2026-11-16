# iPhone MCP

Let an agent take control of your iPhones, from A to Z. It doesn't stop at tapping a screen. It runs the whole phone for you: it checks which phones are online, opens and closes apps, taps, swipes and types, sends photos and videos to a phone, builds and runs automations across your phones, and tells you who used which phone and for how long. You ask in plain words, it does the work.

Control real iPhones from Claude, ChatGPT, VS Code and Codex. Your AI assistant can see an iPhone's screen, tap, swipe, type, press buttons and open apps, on real iPhones hosted by [ALI Remote](https://aliremote.com).

No Mac, no Xcode, no USB cable and no simulator. One URL connects your assistant to the official ALI Remote MCP server:

```
https://api.aliremote.com/api/mcp
```

Sign-in is OAuth in the browser. There is no API key to paste.

## Before you start

The server works with the iPhones on your ALI Remote account. [Create an account](https://app.aliremote.com/signup) and get phones on it, then connect your assistant below. Plans are on the [pricing page](https://aliremote.com/pricing).

## What you can ask

- "Which of my phones are offline?"
- "Take a screenshot of phone 12 and tell me what is on screen."
- "On phone 12, open Settings and tell me which iOS version it runs."
- "Do this on phone 12 first. If it works, do the same on phones 13 to 20 and give me a table."
- "Who used phone 12 yesterday, and for how long?"

More in [examples/prompts.md](examples/prompts.md).

## Connect

### Claude Code

Install the plugin. It adds the server and a skill that teaches Claude to drive phones well.

```
/plugin marketplace add ALI-remote/iphone-mcp
/plugin install iphone@ali-remote
```

Then type `/mcp`, pick `ali` and choose Authenticate.

Or add only the server:

```
claude mcp add --transport http ali https://api.aliremote.com/api/mcp
```

### Claude Desktop and claude.ai

1. Open Customize, then Connectors, and choose Add custom connector.
2. Paste `https://api.aliremote.com/api/mcp`.
3. Select Add, then Connect, and approve the sign-in.

A connector added on claude.ai also shows up in the desktop and mobile apps.

### VS Code

[Install in VS Code](https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522ali%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fapi.aliremote.com%252Fapi%252Fmcp%2522%257D)

Or by hand:

1. Open the Command Palette and run MCP: Add Server.
2. Choose HTTP and paste `https://api.aliremote.com/api/mcp`.
3. Name it `ali` and approve the sign-in when VS Code asks.

### Codex CLI

```
codex mcp add ali --url https://api.aliremote.com/api/mcp
codex mcp login ali
```

### ChatGPT

Turn on developer mode in ChatGPT's settings, then add an app with `https://api.aliremote.com/api/mcp` and OAuth sign-in.

### Other assistants

Any MCP client that supports remote servers over streamable HTTP with OAuth 2.1 can connect with the same URL.

## Driving phones well

These are real phones, so a few habits matter:

- Screenshot first, then decide where to tap.
- Read tap positions off the screenshot and send them unscaled.
- Get a task working on one phone before running it on many.

The Claude Code plugin includes these as a skill. For other assistants, give them [skills/driving-iphones/SKILL.md](skills/driving-iphones/SKILL.md).

## FAQ

**Are these real iPhones?**
Yes. Physical iPhones hosted by ALI Remote, not simulators or emulators.

**Do I need a Mac, Xcode or a cable?**
No. Everything runs on ALI Remote's side. You only need an assistant that supports MCP.

**Does it work without an ALI Remote account?**
No. The server only shows the phones on your own account.

**Which assistants work?**
Claude Code, Claude Desktop, claude.ai, VS Code, Codex CLI and ChatGPT.

**Does the assistant act on its own?**
It does what you ask, through your account and your permissions. Your assistant asks you to approve tool calls according to its own settings.

**Is there an API as well?**
Yes. ALI Remote also has a REST API for your own code. See the [developer docs](https://app.aliremote.com/docs).

## Links

- [ALI Remote](https://aliremote.com)
- [Pricing](https://aliremote.com/pricing)
- [Developer docs](https://app.aliremote.com/docs)
- [llms.txt](https://app.aliremote.com/llms.txt)
- [Privacy](https://aliremote.com/legal/privacy)

## License

MIT
