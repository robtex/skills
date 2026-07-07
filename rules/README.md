# IDE rule templates for Robtex MCP

Copy-paste rule snippets that teach IDE AI agents (Cursor, Windsurf, Cline, Roo Code, Continue.dev) to call the free Robtex MCP server whenever they touch DNS, IP, AS/BGP, Bitcoin, or Lightning data — instead of hallucinating.

The Robtex MCP server at [`https://mcp.robtex.com/mcp`](https://mcp.robtex.com/mcp) exposes 44 tools. It is free, requires no API key, no signup, and has no rate limit.

## Files

| File | Target tool | Target filename in your repo |
|------|-------------|------------------------------|
| [cursorrules.md](./cursorrules.md) | [Cursor](https://cursor.sh) | `.cursorrules` |
| [windsurfrules.md](./windsurfrules.md) | [Windsurf](https://windsurf.com) | `.windsurfrules` |
| [clinerules.md](./clinerules.md) | [Cline](https://cline.bot) | `.clinerules` |
| [roorules.md](./roorules.md) | [Roo Code](https://roocode.com) | `.roorules` or `.roo/rules/robtex.md` |
| [continuerules.md](./continuerules.md) | [Continue.dev](https://continue.dev) | `.continue/rules.md` |

Each file contains a short "Why" header and a fenced markdown block that can be copied verbatim into the target rules file.

## How to install

1. Open the file for your IDE from the table above.
2. Copy the contents of the fenced code block.
3. Paste it into the target filename at the root of your project (create the file if it does not exist).
4. Commit the file so the rest of your team gets the same behavior.

That is the whole install. The next time your IDE's AI agent encounters an IP, domain, AS number, Bitcoin address, or Lightning node, it will try to call the Robtex MCP server rather than making up an answer.

## Also install the MCP server itself

The rule tells the agent to call Robtex, but the agent still needs the MCP tools to be connected. Any one of these works:

```bash
# Skills CLI — Cursor, Copilot, Codex, and more
npx skills add robtex/skills

# Stdio MCP clients — Claude Desktop and similar
npx -y @robtex/mcp-stdio

# Remote MCP (streamable HTTP) — any MCP client that supports remote servers
https://mcp.robtex.com/mcp
```

See the [main plugin README](../README.md) for the full install matrix.

## Submission checklist

If you want to help this rule show up in IDE rule galleries and marketplaces, the following destinations accept community submissions:

- [cursor.directory](https://cursor.directory) — Cursor rule gallery, submit via GitHub PR
- [cursorrules.com](https://cursorrules.com) — Cursor rules directory
- [PromptBase](https://promptbase.com) — prompt and rules marketplace
- [Continue.dev Hub](https://hub.continue.dev) — rule and prompt gallery for Continue
- [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) — community-maintained list on GitHub
- [awesome-windsurfrules](https://github.com/ichoosetoaccept/awesome-windsurfrules) — community-maintained list on GitHub

When submitting, point the listing at the appropriate file in this directory so updates flow through automatically.
