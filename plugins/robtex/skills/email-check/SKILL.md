---
name: email-check
description: "Verify an email address — SMTP validation, MX records, catch-all detection, TLS support, and domain reputation"
---

# Email Verification

Verify the email address: **$ARGUMENTS**

Run these checks in parallel:

1. `check_email` — SMTP verification (MX lookup, RCPT TO validation, catch-all detection, TLS support)
2. `lookup_dns` on the domain part — MX, SPF (TXT), DMARC, DKIM records
3. `domain_reputation` on the domain — is it a known disposable/temporary email provider?
4. `domain_ranking` on the domain — popularity ranking (legitimate domains tend to rank)

Present a clear verdict:
- **VALID** — mailbox exists, domain is legitimate, not a catch-all
- **RISKY** — catch-all domain (accepts any address), or low-reputation domain
- **INVALID** — mailbox rejected, domain has no MX, or domain is disposable/blocklisted

Include: delivery confidence score, mail server details, SPF/DMARC/DKIM status, TLS version, and any reputation flags.
