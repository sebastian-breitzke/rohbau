# Authentication

## My Decision

- **Spürhund:** WorkOS (stays for now — free to 1M MAU, can't justify €70/mo for 50 beta users)
- **Fachwerk:** Ory Kratos self-hosted (Docker-Compose, €0 software, Mittelstand customers care about EU jurisdiction)

## The Options

### WorkOS (San Francisco)

- Free up to 1M MAU. No asterisk. SSO, MFA, session management.
- Best free tier in the auth space by far.
- US company, CLOUD Act applies.
- Great DX, good docs, fast integration.
- **Verdict:** Hard to beat at zero cost. The sovereignty trade-off is real but at beta scale it doesn't matter.

### Ory Network (Munich)

- Open source core (Kratos, Hydra, Oathkeeper, Keto).
- OIDC/OAuth2/SAML. Self-hostable. EU jurisdiction.
- **Pricing reality:** Development: free. Production: **€70/month**. That's before your first paying customer.
- Took 3 days to even find Ory. Auth0 takes 3 minutes because it's the default answer everywhere.
- Self-hosted Kratos: genuinely €0 software cost, runs in Docker. But you're ops from day one.
- **Verdict:** Great software, painful pricing for validation-stage products. Self-hosted is the move for sovereignty.

### Auth0 / Okta (US)

- Free up to 25,000 MAU.
- Massive ecosystem, every tutorial assumes Auth0.
- US company (Okta), CLOUD Act applies.
- **Verdict:** The default. Works. Not sovereign.

### Zitadel (Lucerne, Switzerland)

- Free tier: 25,000 MAU on cloud.
- Swiss-hosted. GDPR-native.
- Open source, self-hostable.
- Less known, smaller community.
- **Verdict:** Interesting EU-adjacent alternative. Worth watching.

### Firebase Auth (Google)

- Unlimited email/password users free.
- US (Google), not sovereign.
- **Verdict:** Generous but fully US-dependent.

## The Free Tier Gap

| Provider | HQ | Free Tier | Production Cost |
|----------|-----|-----------|-----------------|
| WorkOS | US | 1M MAU | Free |
| Auth0 | US | 25K MAU | Usage-based |
| Firebase Auth | US | Unlimited | Free |
| Supabase Auth | US | 50K MAU | Free |
| Ory Network | DE | Dev only | €70/mo |
| Zitadel | CH | 25K MAU | Usage-based |
| Keycloak | Open Source | Self-host | €4-7/mo VPS |

## The Math

€70 Ory + €5 domain + €4 Hetzner + email + monitoring = €100-150/month fixed costs. That's 30 paying users just to break even on infrastructure. With WorkOS, you can have thousands of users for free while figuring out if the product works.

## What I'd Tell the Next Person

- Building for EU Mittelstand? Self-host Kratos. They'll ask about data residency.
- Validating an idea? Use WorkOS or Auth0. Switch when it matters.
- Don't be dogmatic. Sovereignty is a spectrum, not a switch.
