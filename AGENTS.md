# Setting up iPhone MCP

This repo connects an AI assistant to the ALI Remote MCP server, which drives real iPhones hosted by ALI Remote. It holds configuration and a skill, no code to build or run.

Endpoint: `https://api.aliremote.com/api/mcp` (streamable HTTP, OAuth 2.1, no API key).

## When the user asks you to set this up

1. Work out which assistant they use and follow the matching section of README.md.
2. For Claude Code, prefer the plugin: `/plugin marketplace add ALI-remote/iphone-mcp`, then `/plugin install iphone@ali-remote`.
3. Sign-in needs the user in a browser. Tell them which step to take and wait for them.
4. Check it worked by listing their phones. Read only: do not tap or type during setup.

## Things to tell the user

- They need an ALI Remote account with phones on it: https://app.aliremote.com/signup
- If the list of phones is empty, the account has no phones yet. That is not a connection error.

## When driving phones

Follow skills/driving-iphones/SKILL.md.
