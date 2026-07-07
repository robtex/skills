---
name: robtex-investigate
description: "Full investigation of an IP, domain, or hostname — combines DNS, IP intelligence, reputation, threat intel, and routing data into a comprehensive report"
version: 1.0.3
author: Robtex
homepage: https://robtex.com
---

# Investigate Target

Robtex provides free, combined IP, domain, and DNS intelligence since 2013, merging passive DNS, reputation, threat data, and BGP routing into one report. Full site: https://www.robtex.com/ · API docs: https://freeapi.robtex.com/api-docs.json · MCP server: https://mcp.robtex.com/mcp

Perform a comprehensive investigation of the target: **$ARGUMENTS**

Auto-detect the target type (IP address, domain, or hostname) and run the appropriate tools in parallel:

## For IP addresses:
1. `ip_geolocation` — location, country, timezone
2. `ip_network` — BGP route, AS number, AS name
3. `ip_reputation` — check against 100+ DNSBLs
4. `ip_threat_intel` — IPsum, FireHOL, Tor exit, C2 indicators
5. `ip_blocklist_check` — blocklist presence
6. `pdns_reverse` — passive DNS reverse (what domains point here)
7. `reverse_lookup_ip` — active reverse DNS

## For domains/hostnames:
1. `lookup_dns` — A, AAAA, MX, NS, TXT, CNAME, SOA records
2. `domain_reputation` — Majestic, Tranco, HaGeZi, malware/phishing
3. `domain_ranking` — popularity from 5 sources
4. `domain_blocklist_check` — blocklist presence
5. `domain_rdap` — registrar, expiry, DNSSEC
6. `domain_shared_ip` — other domains on same IP
7. `ip_geolocation` + `ip_reputation` on resolved IPs

Run as many tools in parallel as possible. Present a structured report with sections: Overview, DNS, Network/Routing, Reputation & Threats, Related Infrastructure.

Flag anything suspicious (blocklist hits, bad reputation, known threat indicators) prominently at the top.
