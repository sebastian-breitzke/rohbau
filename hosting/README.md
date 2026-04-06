# Hosting / Deployment

## My Decision

- **Spürhund:** Cloudflare Pages (free tier, instant deploys, zero cost to experiment)
- **Fachwerk:** Hetzner Cloud CX22 (€4.51/mo, Helsinki, GDPR native)

## The Free Tier Gap

This is the most dramatic gap in the entire stack.

### US: Deploy Is a Solved Problem

| Service | HQ | Free Tier | What You Get |
|---------|-----|-----------|-------------|
| Vercel | US | 100 GB bandwidth, serverless functions | Git push → live. SSL, CDN, preview URLs, CI/CD. |
| Cloudflare Pages | US | Unlimited bandwidth, 500 builds/mo | Same. Plus Workers, KV, D1 — entire platform free. |
| Netlify | US | 100 GB bandwidth, 300 build min/mo | Same pattern. |
| Railway | US | $5 free credit/mo | Full backend hosting with DB. |
| Fly.io | US | 3 shared VMs, 3 GB storage | Global edge deployment. |
| Render | US | Static sites free, web services with spin-down | Docker-based, straightforward. |

No credit card. No config. Push to Git, app is live. Throw 10 ideas at the wall for $0.

### EU: Deploying Is a Skill

| Service | HQ | Free Tier | Cheapest | Notes |
|---------|-----|-----------|----------|-------|
| Hetzner Cloud | DE | **No** | €4.51/mo | Exceptional value. No zero tier. |
| Scaleway | FR | Discontinued | €7.02/mo | Had a free tier briefly, pulled it. |
| OVH | FR | **No** | €3.57/mo | Cheap but not free. |
| Uberspace | DE | Pay what you want | €1/mo min | Admirable model. Shared hosting. |
| Clever Cloud | FR | **No** | €5.40/mo | PaaS, no free tier. |
| Northflank | UK | Yes | 2 services, 0.2 vCPU | One of the few EU-adjacent PaaS with a real free tier. |

### Why This Matters

Zero and non-zero are different categories. Zero means try everything. Non-zero means evaluate first.

Running 5 ideas on Vercel: $0/mo. Running 5 ideas on Hetzner: €22.55/mo. That changes behavior across an entire continent of potential founders.

## The Host Europe Story

My domain was at Host Europe. Sounds European. Was acquired by GoDaddy years ago. When I tried to transfer:

1. Discovered a third registrar hidden behind reseller agreements
2. Could not change my DNS servers — the option simply wasn't there
3. Transfer took over a week — 5-day mandatory waiting periods plus weekends
4. The "European" provider was US-owned with none of the American convenience

Cloudflare: pointed DNS, deployed to Pages, live in minutes. Free tier. The irony writes itself.

## Hetzner: The Price-Performance King

My Fachwerk setup on Hetzner CX22:
- 2 vCPU, 4 GB RAM, 40 GB NVMe
- PostgreSQL + Caddy + Elixir/Phoenix app
- Helsinki data center, Finnish jurisdiction, German company
- Total: **€4.42/month**

Cheaper than any US platform at scale. But you configure everything yourself — Nginx/Caddy, SSL, firewall, backups, monitoring. Deploying is a skill, not a button.

## What I'd Tell the Next Person

- Validating ideas? Use Cloudflare Pages or Vercel. Zero friction, zero cost.
- Production EU workload? Hetzner. The €4/mo is the best deal in cloud computing.
- Don't try to self-host on day one if your product doesn't exist yet.
- The missing piece: a Vercel-equivalent PaaS on EU infra with a real free tier. Hetzner's margins could support it — someone build this.
