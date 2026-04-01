---
name: threat-scan
description: "Threat intelligence scan — check IPs and domains against 100+ blocklists, reputation databases, and threat feeds"
---

# Threat Intelligence Scan

Scan the target for threats: **$ARGUMENTS**

Accept one or more targets (IPs, domains, or emails) separated by spaces or commas. For each target, run the appropriate checks in parallel:

## For IP addresses:
1. `ip_reputation` — 100+ DNSBL blocklists with threat categories
2. `ip_threat_intel` — combined IPsum, FireHOL, Tor exits, C2 indicators, AbuseIPDB
3. `ip_blocklist_check` — IPsum score, FireHOL lists, bad ASN
4. `ip_network` — AS info (is it a known-bad hosting provider?)
5. `ip_geolocation` — country (relevant for geo-based threat assessment)

## For domains:
1. `domain_reputation` — Majestic rank, Tranco rank, HaGeZi blocklist, malware/phishing
2. `domain_blocklist_check` — HaGeZi, Steven Black, Blackbook malware, phishing DBs
3. `lookup_dns` — check for suspicious DNS patterns
4. `domain_shared_ip` — neighborhood analysis (other domains on same IP)

## For email addresses:
1. `check_email` — SMTP verification, MX check, catch-all detection, TLS support

Present results as a threat assessment with a clear verdict:
- **CLEAN** — no blocklist hits, good reputation
- **SUSPICIOUS** — minor hits, low-confidence indicators
- **MALICIOUS** — multiple blocklist hits, known threat indicators

For each hit, include: source, category (spam/malware/phishing/C2/botnet), confidence level, and when it was last seen. Sort findings by severity.
