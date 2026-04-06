# Email / Transactional

## My Decision

- **Spürhund:** Not needed yet (no transactional email in beta)
- **Fachwerk:** Postal (self-hosted)

## The Options

### US Providers

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| SendGrid (Twilio) | US | 100 emails/day | Industry default. US-owned. |
| Resend | US | 3,000/month, 100/day | Modern API, good DX. US. |
| Postmark | US | 100 test emails only | $15/mo for 10K. Premium positioning. |
| SES (Amazon) | US | 62K/month (from EC2) | Cheapest at scale. AWS dependency. |

### EU Alternatives — The Bright Spots

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| **Mailjet** | FR (Paris) | 6,000/month, 200/day | Genuine EU free tier. Now owned by Sinch (SE). |
| **Brevo** (ex-Sendinblue) | FR (Paris) | 300/day | Marketing + transactional. French. |
| Postal | Open Source | Self-host | €0 software + VPS cost + IP reputation management |

### The Surprise

Email is one of the few layers where EU actually competes on free tiers. Mailjet (6K/month free) and Brevo (300/day free) are genuine alternatives. French companies, EU data processing.

The catch: Mailjet was acquired by Mailgun/Sinch group. The ownership chain gets murky. But data processing stays EU.

### Self-Hosted: Postal

Running Postal means:
- A dedicated VPS (separate from app server — IP reputation matters)
- DNS setup: SPF, DKIM, DMARC, rDNS
- IP warmup if sending volume grows
- Monitoring deliverability

It works. It's real work. Not recommended unless you need full control.

## What I'd Tell the Next Person

- For most products: Mailjet free tier. French, 6K/month, good enough.
- For full sovereignty: Postal self-hosted, but budget the ops time.
- Don't self-host email unless you actually need to. Deliverability is a full-time job.
