# CI/CD

## My Decision

- **Spürhund:** Cloudflare Pages (auto-deploy on push, built in)
- **Fachwerk:** GitHub Actions (2,000 min/mo free)

## The Options

### US: CI/CD Is Free

| Service | HQ | Free Tier |
|---------|-----|-----------|
| GitHub Actions | US (Microsoft) | 2,000 min/mo (public repos unlimited) |
| Vercel | US | Auto-deploy on push, included |
| Cloudflare Pages | US | 500 builds/month, included |
| Netlify | US | 300 build min/month |
| GitLab CI | US (French origins) | 400 min/month |

### EU: Self-Host or Use GitLab

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| GitLab CI | US/FR | 400 min/month | French origins, US HQ now. |
| Woodpecker CI | Open Source | Self-host | Lightweight, Docker-based. |
| Drone CI | Open Source | Self-host | Harness-owned. |

GitLab is the closest to EU — French founders, open-core, self-hostable. But the company is US-headquartered now.

## What I'd Tell the Next Person

- If your hosting has built-in CI (Cloudflare Pages, Vercel): use it. One less thing.
- Otherwise: GitHub Actions. 2,000 free minutes covers most SMB needs.
- Self-hosting CI is the last thing you should spend time on. It adds nothing to your product.
