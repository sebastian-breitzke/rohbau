# AI Models

## My Decision

- **Both products:** Anthropic Claude (US). Honest. Behind an adapter pattern for future portability.

## The State of EU AI

### Mistral AI (Paris)

- Strongest European contender.
- ~2% of global LLM market (ECFR data).
- Open-weight models, good for self-hosting.
- Mistral Medium: "90%+ of premium performance" at competitive pricing.
- Not competing at the frontier with Claude Opus, GPT-4.5, or Gemini for the hardest tasks.
- **Verdict:** Real and improving. Not yet a drop-in replacement for frontier models.

### Aleph Alpha (Heidelberg)

- Raised €500M+ to build "Europe's OpenAI."
- **Quit the frontier LLM race in September 2024.**
- CEO Jonas Andrulis: "Just having a European LLM is not sufficient as a business model."
- Pivoted to PhariaAI — middleware/consulting that helps enterprises use whatever LLM they want.
- The honest lesson: half a billion euros could not close the gap with US model labs.

### Other EU Players

- DeepL (Cologne): Best-in-class translation. 500K chars/month free. Not general-purpose AI.
- Hugging Face (Paris/US dual HQ): Infrastructure, not models. Hosts everything.
- EU AI Factory: Funding new efforts. Years from parity.

## The Free Tier Gap

| Provider | HQ | Free Tier | Notes |
|----------|-----|-----------|-------|
| Google Gemini | US | 15 RPM free, Flash generous | Best free offering |
| Groq | US | Generous free inference | Rate-limited but real |
| OpenAI | US | ~$5 initial credits | Then pay-as-you-go |
| Anthropic | US | No free API tier | $5 minimum |
| Mistral | FR | Limited free access | Rate-limited on some models |
| Aleph Alpha | DE | No public free tier | Enterprise only |

## The Adapter Pattern

Both my products treat AI models as swappable:
- One config change to switch from Claude to Mistral
- Business logic doesn't know which model it's talking to
- When EU models catch up, switching is a config deploy

This is the only honest position: use the best tool now, architect for portability.

## What I'd Tell the Next Person

- Use Anthropic or OpenAI. Be honest about it. Don't pretend Mistral is equivalent if your use case needs frontier quality.
- Build the adapter pattern from day one. It's cheap insurance.
- Watch Mistral. They're the most credible EU path to competitive models.
- Aleph Alpha's pivot is the cautionary tale: you can't will competitive AI into existence with funding alone.
