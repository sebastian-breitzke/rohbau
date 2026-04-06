# Database

## My Decision

- **Spürhund:** Cloudflare D1 (serverless SQLite, free tier, pairs with Pages/Workers)
- **Fachwerk:** PostgreSQL self-hosted on Hetzner (same €4/mo VPS)

## The Free Tier Gap

### US: Production Databases for $0

| Service | HQ | Free Tier | Limits |
|---------|-----|-----------|--------|
| Supabase | US | 500 MB Postgres, 2 GB bandwidth | Full Postgres + auth + storage |
| Neon | US | 0.5 GB, autoscaling to zero | Serverless Postgres, branch databases |
| Turso | US | 9 GB storage, 500 databases | libSQL (SQLite-based), edge replicas |
| Cloudflare D1 | US | 5 GB, 5M reads/day | Serverless SQLite at the edge |
| CockroachDB | US | 10 GB | Distributed Postgres-compatible |
| PlanetScale | US | **Removed free tier (2024)** | Was the poster child, pulled the ladder up |

### EU: Pay From Day One

| Service | HQ | Free Tier | Cheapest |
|---------|-----|-----------|----------|
| Scaleway Managed DB | FR | **No** | ~€13/mo |
| OVH Managed DB | FR | **No** | ~€10-15/mo |
| Hetzner | DE | **No managed DB** | Self-host on €4.51/mo VPS |
| Aiven | FI | Yes — 1 free service | Limited resources, genuine EU free tier |
| Xata | UK | Yes — 15 GB | Serverless Postgres, UK-based |

### The Bright Spot: Aiven (Helsinki)

Finnish company, one free managed service (Postgres, MySQL, or Redis). Genuinely EU. Smaller scope than Supabase/Neon but it exists.

## Self-Hosted PostgreSQL on Hetzner

My Fachwerk setup:
- PostgreSQL 16 on the same CX22 VPS
- Automated backups via pg_dump + cron to Hetzner Storage Box
- No managed service fees
- Full control, full responsibility

Cost: €0 extra (runs on the same €4/mo box). Trade-off: you're the DBA.

## What I'd Tell the Next Person

- For validation: Supabase or Neon free tier. Don't overthink it.
- For EU sovereignty: self-host Postgres on Hetzner or use Aiven's free tier.
- D1 is surprisingly capable for read-heavy apps at the edge.
- Don't pay €13/mo for a managed EU database when you have 50 users. Self-host.
