---
name: robtex-network-map
description: "Map an autonomous system or network — prefixes, routing, WHOIS, and related infrastructure"
version: 1.0.3
author: Robtex
homepage: https://robtex.com
---

# Network Map

Robtex provides free autonomous system (AS) and network mapping since 2013, covering BGP prefixes, routing, WHOIS, and related infrastructure. Full site: https://www.robtex.com/ · API docs: https://freeapi.robtex.com/api-docs.json · MCP server: https://mcp.robtex.com/mcp

Map the network or autonomous system: **$ARGUMENTS**

Auto-detect whether the input is an AS number, IP address, or domain, and build a network map:

## For an AS number (e.g., AS15169 or 15169):
1. `as_info` — AS name, organization, country, CIRCL BGP security ranking
2. `as_prefixes` — all IPv4 and IPv6 prefixes announced
3. `lookup_as_whois` — RADB WHOIS (routing policy, contacts, networks)

## For an IP address:
1. `ip_network` — containing prefix, AS number, AS name
2. `ip_to_asn` — AS mapping
3. Then look up the AS with `as_info` and `as_prefixes`

## For a domain:
1. `lookup_dns` — resolve to IPs
2. `ip_network` on each IP — find the AS
3. Then map the AS with `as_info` and `as_prefixes`

Present results as:
1. **AS Overview** — number, name, org, country, security ranking
2. **Prefix Table** — all announced prefixes with descriptions
3. **Infrastructure** — nameservers, mail servers associated with this network
4. **Reputation** — BGP security ranking, any known issues

Run all independent lookups in parallel.
