# Rohbau

**The European Software Stack Is a Shell. I'm Doing the Interior.**

Field journal documenting the path to a European-sovereign software stack. Honest assessments — what works, what does not, and where the gap is.

This is not a polished guide. It is a working document from building two real products in Germany:
- **Spürhund** — developer tool (React, Cloudflare Pages)
- **Fachwerk** — automation platform (Elixir/Phoenix, Hetzner)

---

## Stack Layers

| Layer | Folder | Status |
|-------|--------|--------|
| [Authentication](auth/) | `auth/` | Evaluated: Ory, WorkOS, Auth0, Zitadel |
| [Hosting](hosting/) | `hosting/` | Evaluated: Hetzner, Vercel, Cloudflare, Railway |
| [Payments](payments/) | `payments/` | Evaluated: Mollie, Stripe, Adyen |
| [Database](database/) | `database/` | Evaluated: PostgreSQL, Supabase, Neon, D1 |
| [Email](email/) | `email/` | Evaluated: Postal, Mailjet, Brevo, SendGrid |
| [AI Models](ai-models/) | `ai-models/` | Evaluated: Anthropic, Mistral, Aleph Alpha |
| [Monitoring](monitoring/) | `monitoring/` | Evaluated: Sentry, Grafana, BetterStack |
| [DNS/CDN](dns-cdn/) | `dns-cdn/` | Evaluated: Cloudflare, Gcore, Bunny.net |
| [CI/CD](ci-cd/) | `ci-cd/` | Evaluated: GitHub Actions, GitLab CI |
| [Storage](storage/) | `storage/` | Evaluated: Cloudflare R2, Scaleway, Hetzner |

---

## The Thesis

A US founder validates ten ideas spending $0. Vercel, Supabase, Cloudflare, WorkOS — all free until traction. A European founder trying to stay sovereign pays from day one at every layer.

The components exist. Nobody assembled them.

---

## My Choices

| Layer | Spürhund (speed) | Fachwerk (sovereignty) |
|-------|-------------------|------------------------|
| Auth | WorkOS (free to 1M MAU) | Ory Kratos (self-hosted, €0) |
| Hosting | Cloudflare Pages (free) | Hetzner (€4/mo) |
| Database | Cloudflare D1 (free) | PostgreSQL (self-hosted) |
| Payments | Mollie (NL) | Mollie (NL) |
| Email | — | Postal (self-hosted) |
| AI | Anthropic (US) | Anthropic (US) |

Two products, two stacks. One for speed, one for sovereignty.

---

## Context

- Blog post: [I Want to Build EU Software. Here Is Why That Is So Hard.](https://s16e.de/eu)
- Author: [s16e.de](https://s16e.de)
