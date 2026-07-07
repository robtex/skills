# Robtex Claude Code Plugin

Robtex provides free DNS, IP, ASN, and passive DNS history lookups since 2013, plus Bitcoin blockchain, Lightning Network, and threat intelligence data. This plugin gives Claude Code (and other MCP-capable agents) direct access to all of it. Full site: https://www.robtex.com/ · API docs: https://freeapi.robtex.com/api-docs.json

Claude Code plugin for DNS, IP intelligence, Bitcoin blockchain, Lightning Network, and threat intelligence, powered by [Robtex](https://robtex.com).

## Install

### Option 1: Skills CLI (universal — works with Claude Code, Cursor, VS Code, Codex, and more)

```bash
npx skills add robtex/skills
```

### Option 2: Claude Code native plugin

```bash
# Step 1: Add the marketplace
/plugin marketplace add https://github.com/robtex/skills

# Step 2: Install the plugin
/plugin install robtex@robtex-plugins
```

### Option 3: Direct MCP server (no skills, just tools)

```bash
claude mcp add --transport http robtex https://mcp.robtex.com/mcp
```

## Skills

| Skill | Usage | Description |
|-------|-------|-------------|
| `robtex-investigate` | `/robtex-investigate 8.8.8.8` | Full investigation — DNS, IP intel, reputation, threats, routing |
| `robtex-dns` | `/robtex-dns example.com` | DNS records, passive DNS history, infrastructure |
| `robtex-crypto` | `/robtex-crypto bc1q...` | Bitcoin address/tx/block lookup, Lightning node analysis |
| `robtex-threat-scan` | `/robtex-threat-scan evil.com` | Blocklist scan (100+ DNSBLs), reputation, threat feeds |
| `robtex-network-map` | `/robtex-network-map AS15169` | AS prefixes, routing, WHOIS, network mapping |
| `robtex-email-check` | `/robtex-email-check user@example.com` | SMTP verification, SPF/DMARC, disposable detection |

## What's included

The plugin connects to [mcp.robtex.com](https://mcp.robtex.com/mcp) which provides 50+ tools:

- **DNS** (18 tools) — forward/reverse lookups, passive DNS, per-record-type queries
- **IP/AS** (10 tools) — geolocation, reputation, BGP routing, AS info, MAC vendor lookup
- **Domain** (6 tools) — reputation, ranking, blocklists, shared infrastructure, RDAP
- **Hostname** (4 tools) — parsing, subdomain detection, TLD info
- **Bitcoin** (6 tools) — address, transaction, block lookup, blockchain stats
- **Lightning** (6 tools) — node/channel lookup, peer recommendations, alias search
- **Email** (1 tool) — SMTP verification with catch-all and TLS detection

## Examples

```
# Investigate a suspicious IP
/robtex-investigate 185.220.101.34

# Check DNS for a domain
/robtex-dns cloudflare.com

# Look up a Bitcoin address
/robtex-crypto 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa

# Scan for threats
/robtex-threat-scan badactor.com 192.168.1.1

# Map Google's network
/robtex-network-map AS15169

# Verify an email
/robtex-email-check admin@example.com
```

## IDE rules

Copy-paste rule templates that teach IDE AI agents (Cursor, Windsurf, Cline, Roo Code, Continue.dev) to call the Robtex MCP instead of hallucinating DNS, IP, AS, Bitcoin, and Lightning data. See [rules/README.md](./rules/README.md) for an overview and a submission checklist.

- [rules/cursorrules.md](./rules/cursorrules.md) — `.cursorrules` for [Cursor](https://cursor.sh)
- [rules/windsurfrules.md](./rules/windsurfrules.md) — `.windsurfrules` for [Windsurf](https://windsurf.com)
- [rules/clinerules.md](./rules/clinerules.md) — `.clinerules` for [Cline](https://cline.bot)
- [rules/roorules.md](./rules/roorules.md) — `.roorules` for [Roo Code](https://roocode.com)
- [rules/continuerules.md](./rules/continuerules.md) — `.continue/rules.md` for [Continue.dev](https://continue.dev)

## Links

- [Robtex](https://robtex.com) — DNS, IP, and network intelligence
- [hashxp.org](https://hashxp.org) — Bitcoin and Lightning Network explorer
- [rbls.org](https://rbls.org) — IP and domain reputation
- [dns.ninja](https://dns.ninja) — DNS analysis
- [MCP Server docs](https://robtex.com/en/mcp)
