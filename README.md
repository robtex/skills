# Robtex Claude Code Plugin

Claude Code plugin for DNS, IP intelligence, Bitcoin blockchain, Lightning Network, and threat intelligence — powered by [Robtex](https://robtex.com).

## Install

```bash
# Step 1: Add the marketplace (full GitHub URL required)
/plugin marketplace add https://github.com/robtex/claude-plugins

# Step 2: Install the plugin
/plugin install robtex@robtex-plugins
```

## Skills

| Skill | Usage | Description |
|-------|-------|-------------|
| `/robtex:investigate` | `/robtex:investigate 8.8.8.8` | Full investigation — DNS, IP intel, reputation, threats, routing |
| `/robtex:dns` | `/robtex:dns example.com` | DNS records, passive DNS history, infrastructure |
| `/robtex:crypto` | `/robtex:crypto bc1q...` | Bitcoin address/tx/block lookup, Lightning node analysis |
| `/robtex:threat-scan` | `/robtex:threat-scan evil.com` | Blocklist scan (100+ DNSBLs), reputation, threat feeds |
| `/robtex:network-map` | `/robtex:network-map AS15169` | AS prefixes, routing, WHOIS, network mapping |
| `/robtex:email-check` | `/robtex:email-check user@example.com` | SMTP verification, SPF/DMARC, disposable detection |

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
/robtex:investigate 185.220.101.34

# Check DNS for a domain
/robtex:dns cloudflare.com

# Look up a Bitcoin address
/robtex:crypto 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa

# Scan for threats
/robtex:threat-scan badactor.com 192.168.1.1

# Map Google's network
/robtex:network-map AS15169

# Verify an email
/robtex:email-check admin@example.com
```

## Alternative: Manual MCP setup

If you prefer to add the MCP server directly without installing the plugin:

```bash
claude mcp add --transport http robtex https://mcp.robtex.com/mcp
```

This gives you all 50+ tools but without the curated skills above.

## Links

- [Robtex](https://robtex.com) — DNS, IP, and network intelligence
- [hashxp.org](https://hashxp.org) — Bitcoin and Lightning Network explorer
- [rbls.org](https://rbls.org) — IP and domain reputation
- [dns.ninja](https://dns.ninja) — DNS analysis
- [MCP Server docs](https://robtex.com/en/mcp)
