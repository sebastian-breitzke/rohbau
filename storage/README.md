# Object Storage

## My Decision

- **Spürhund:** Cloudflare R2 (free tier, zero egress, S3-compatible)
- **Fachwerk:** Hetzner Object Storage (€1.18/TB/mo, S3-compatible)

## The Options

### US: Absurdly Generous

| Service | HQ | Free Tier | Egress |
|---------|-----|-----------|--------|
| Cloudflare R2 | US | 10 GB, 10M ops/month | **Zero. Forever.** |
| AWS S3 | US | 5 GB, 12-month only | Expensive after free tier |
| Backblaze B2 | US | 10 GB forever | Free via Cloudflare partnership |

R2's zero-egress model is game-changing. You never pay for downloads.

### EU: Cheap, Not Free

| Service | HQ | Free Tier | Cost |
|---------|-----|-----------|------|
| **Scaleway Object Storage** | FR | 75 GB free, 75 GB transfer | Genuine EU free tier |
| Hetzner Object Storage | DE | No | €1.18/TB/mo. S3-compatible. |
| OVH Object Storage | FR | No | ~€0.01/GB/mo |

### Scaleway: The EU Bright Spot

75 GB free storage + 75 GB transfer/month. S3-compatible. French. This is one of the strongest EU free tiers across any category.

## What I'd Tell the Next Person

- For zero-cost: Cloudflare R2. Zero egress is unique.
- For EU sovereignty with free tier: Scaleway. 75 GB is plenty for most apps.
- For EU sovereignty at scale: Hetzner. €1.18/TB is absurdly cheap.
