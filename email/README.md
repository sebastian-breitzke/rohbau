# Email / Transactional

## My Decision

- **Spürhund:** Resend (US, eu-west-1 region). 6 minutes from signup to first mail in production.
- **Fachwerk:** TBD. Postal (self-hosted) or Resend.

## What Actually Happened

### Mailjet (Paris) — Blocked before first mail

Signed up. Configured domain. Got blocked immediately — before sending a single email. No reason given. No transparency. No recourse. The "European alternative" locked me out of my own account with zero explanation.

### Resend (San Francisco, eu-west-1) — 6 minutes to production

15:31 — Account confirmed.
15:33 — "Hello World" first email received.
15:37 — Domain verified, first real transactional email from Spürhund delivered.

One-click Cloudflare domain detection. Auto-configured DNS records. EU region (Ireland) selected automatically. From zero to production emails in 6 minutes.

**This is the gap the blog post is about.** The EU provider blocked me. The US provider with EU hosting got me live in minutes.

## The Options

### US Providers

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| Resend | US (SF) | 3,000/month, 100/day | Modern API, great DX, eu-west-1 available. |
| SendGrid (Twilio) | US | 100 emails/day | Industry default. |
| Postmark | US | 100 test emails only | $15/mo for 10K. |
| SES (Amazon) | US | 62K/month (from EC2) | Cheapest at scale. |

### EU Providers

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| **Mailjet** | FR (Paris) | 6,000/month, 200/day | Blocked my account before first send. No reason given. |
| **Brevo** (ex-Sendinblue) | FR (Paris) | 300/day | Marketing + transactional. Not tested yet. |
| Postal | Open Source | Self-host | €0 software + VPS + IP reputation management. Real work. |

## The Sovereignty Question

Resend with eu-west-1 means:
- Emails sent from Ireland (EU data center)
- But: Resend is a US company. CLOUD Act applies regardless of region.
- Same situation as AWS eu-west-1 or Stripe's Ireland entity.

Better than US-region. Not truly sovereign. The pragmatic middle ground.

## What I'd Tell the Next Person

- Try Mailjet first if you want EU. But have a backup plan ready because they might block you.
- Resend with eu-west-1 is the pragmatic pick. Great DX, EU region, not sovereign.
- Don't self-host email unless you genuinely need to. Deliverability is a full-time job.
- The painful truth: the best EU email DX I found was a US company hosting in Ireland.
