# DNS / CDN

## My Decision

- **Both products:** Cloudflare (US). DNS + CDN + DDoS + edge platform, all free.

## The Uncomfortable Truth

Cloudflare's free tier is unmatched globally. Not just CDN — an entire edge platform:
- DNS hosting
- CDN with unlimited bandwidth
- DDoS protection
- SSL certificates
- Workers (100K requests/day)
- R2 storage (10 GB)
- Pages (unlimited sites)

There is no EU equivalent. Full stop.

## EU Alternatives

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| **Gcore** | LU (Luxembourg) | 1 TB CDN/month | Genuine EU free tier. CDN only. |
| Bunny.net | SI (Slovenia) | No | $0.01/GB. Cheapest EU CDN. Min $10 deposit. |
| KeyCDN | CH | No | $0.04/GB. Min $49 deposit. |
| Hetzner DNS | DE | Yes — DNS only | Free DNS hosting. No CDN. |

### Gcore: The Bright Spot

Luxembourg-based. 1 TB/month free CDN is competitive for most SMB products. But it's CDN only — no edge compute, no storage, no Workers equivalent.

## What I'd Tell the Next Person

- Use Cloudflare. The free tier is too good to ignore.
- If you need EU-only CDN: Gcore (free) or Bunny.net (cheapest).
- Hetzner DNS is free and EU — use it for DNS if you don't want Cloudflare managing your nameservers.
- This is the layer where pragmatism wins over sovereignty. Nobody is building a competing edge platform in the EU anytime soon.
