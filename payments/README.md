# Payments

## My Decision

- **Spürhund:** Beta free for 3 months. Mollie planned for paid tier.
- **Fachwerk:** Mollie (NL) — EU payment methods native.
- Stripe fully removed from Spürhund codebase (April 2026).

## The DX Gap: Stripe vs Mollie

This is the layer where the trade-off hurts most.

### Stripe (San Francisco)

- Hosted Checkout: one API call, done.
- Billing Portal: self-service plan changes, cancel, invoices — hosted by Stripe.
- Subscription engine: proration, trials, coupons, usage-based, metered billing.
- SDKs in every language including community Elixir lib.
- Test mode with scenario simulation, CLI for local webhook testing.
- **No monthly fee.** Pay per transaction only.
- 1.5% + €0.25 per EU card transaction.

### Mollie (Amsterdam)

- Clean REST API. No hosted checkout portal equivalent.
- Subscriptions: basic recurring charges. No proration, no usage-based, no self-service portal.
- For subscriptions you need: create customer → first payment (sequenceType="first") → create subscription with startDate.
- **Everything Stripe hands you, you build yourself:** cancel flow, plan change, billing history, next payment date display.
- No official Elixir SDK. REST API directly.
- **No monthly fee.** Pay per transaction only.
- 1.8% + €0.25 per EU card transaction (slightly more expensive).
- SEPA DD: €0.25 (cheaper than Stripe's €0.35).

### The Honest Comparison

| Dimension | Stripe | Mollie |
|-----------|--------|--------|
| EU Payment Methods | Good (iDEAL, SEPA, Bancontact) | Better (+ Twint, Payconiq, PayPal native) |
| DX / API Quality | Best in class | Good, not Stripe-level |
| Subscription Billing | Full platform | Basic recurring only |
| Self-Service Portal | Hosted, free | Build it yourself |
| Docs + Community | Industry benchmark | Good, smaller |
| Elixir SDK | Community (battle-tested) | None official |
| Data Residency | EU entity (Ireland) but US parent, CLOUD Act | Dutch, DNB-regulated, EU-only data |
| Card Pricing | 1.5% + €0.25 | 1.8% + €0.25 |

### The Mollie Odyssey (My Experience)

I spent an afternoon removing Stripe from Spürhund. Not replacing it — just removing it. Stripe had: checkout flow, billing portal redirect, webhook handlers, plan state sync. All gone.

Rebuilding this on Mollie will take days because every piece Stripe handed me, I now build:
- Customer creation + mandate flow
- Subscription scheduling with startDate for beta-free period
- Cancel/change plan UI
- Webhook handlers for payment status
- Billing status display

For the 3-month beta free period on Mollie:
- Create customer, authorize payment method (sequenceType="first")
- Create subscription with startDate = today + 3 months
- Premium features active immediately, first charge in 3 months

### Pricing Gap at SMB Scale

At 10K EUR/month card volume, the price difference is ~€30/month. Irrelevant. At beta scale with 50 users: noise.

## What I'd Tell the Next Person

- If complex billing is on your roadmap (usage-based, proration, self-service): Stripe or Stripe + eventual migration.
- If your customers are EU Mittelstand and sovereignty matters: Mollie. Budget the extra dev time.
- If you're in beta: don't integrate payments at all. Ship free, validate, then pick.
- Consider: Mollie for payment processing + Lago (open source) for billing logic if you need both EU sovereignty and complex billing.
