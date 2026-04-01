---
name: dns
description: "DNS lookup and analysis — forward/reverse records, passive DNS history, nameserver and mail server infrastructure"
---

# DNS Lookup

Perform DNS analysis for: **$ARGUMENTS**

Auto-detect what the user wants based on the input:

## For a hostname/domain:
1. `lookup_dns` — all record types (A, AAAA, MX, NS, TXT, CNAME, SOA)
2. `parse_hostname` — eTLD, registered domain, subdomain breakdown
3. `pdns_forward` — passive DNS history (what IPs it has pointed to)
4. `domain_shared_ns` — other domains on the same nameservers
5. `domain_shared_mx` — other domains on the same mail servers

## For an IP address:
1. `dns_ptr` — reverse DNS (PTR record)
2. `reverse_lookup_ip` — hostnames pointing to this IP
3. `pdns_reverse` — passive DNS reverse lookup
4. `historic_reverse_lookup_ip` — historical hostnames

## For a nameserver or mail server:
1. `reverse_lookup_ns` or `reverse_lookup_mx` — domains using this server
2. `historic_reverse_lookup_ns` or `historic_reverse_lookup_mx` — historical usage

Run lookups in parallel. Present results in a clean table format. Highlight any unusual findings (mismatched records, missing expected records, suspiciously recent changes in passive DNS).
