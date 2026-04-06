# Monitoring / Error Tracking

## My Decision

- **Spürhund:** Client-side only, no server monitoring needed yet
- **Fachwerk:** Grafana + Loki (self-hosted, or Grafana Cloud free tier)

## The Options

### US: Generous Free Tiers

| Service | HQ | Free Tier |
|---------|-----|-----------|
| Sentry | US | 5K errors/mo, 10K perf transactions |
| Grafana Cloud | US | 10K metrics, 50 GB logs, 50 GB traces |
| Datadog | US | 5 hosts, 1-day retention (very limited) |
| LogRocket | US | 1,000 sessions/mo |

Sentry's free tier is best-in-class. Grafana Cloud's free tier is surprisingly generous.

### EU: Slim Pickings

| Service | HQ | Free Tier | Notes |
|---------|-----|-----------|-------|
| BetterStack | CZ (Prague) | 10 monitors, status page | Uptime monitoring. Logs start at $25/mo. |
| GlitchTip | Open Source | Self-host | Lightweight Sentry alternative |
| Grafana stack | Open Source | Self-host | Prometheus + Loki + Grafana. Needs 4+ GB RAM. |

### The Grafana Sweet Spot

Grafana Cloud is US-headquartered but the stack is fully open source. Self-hosting Grafana + Loki + Prometheus on Hetzner gives you EU data residency with world-class tooling. The trade-off: ops burden, minimum 4 GB RAM.

## What I'd Tell the Next Person

- For quick error tracking: Sentry free tier. No sovereign alternative comes close.
- For logs and metrics with EU data: self-host Grafana stack on Hetzner or use Grafana Cloud free tier.
- BetterStack for uptime monitoring — Czech company, real free tier.
- Don't self-host monitoring until your product actually needs it. Over-monitoring an app with 50 users is waste.
