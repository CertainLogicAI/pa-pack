# Personal Assistant Pack

A curated, opinionated stack of tools and workflows for building effective personal assistant agents. Rather than prescribing a single monolithic persona, Personal Assistant Pack provides modular components that practitioners can mix, match, and extend.

## What It Is

- A **reference architecture** for personal assistant setups
- A **collection of tested prompt patterns** for common PA tasks
- A **workflow library** (scheduling, triage, drafting, follow-up)
- A **skills compatibility matrix** showing which tools work well together

## What It Is NOT

- Not a one-size-fits-all solution — you will need to adapt it
- Not a replacement for domain-specific skills (finance, legal, medical)
- Not a guarantee that your PA will never make mistakes
- Not an autonomous system; it is a set of building blocks

## Components

| Component | Purpose | Status |
|-----------|---------|--------|
| `triager` | Inbox/message triage with priority scoring | Reference |
| `drafter` | Context-aware email/message drafting | Reference |
| `scheduler` | Calendar conflict detection and suggestions | Reference |
| `followup` | Reminder and deadline tracking | Reference |
| `context-kernel` | Session context management pattern | Documented |

## Installation

### OpenClaw

```bash
cp -r pa-pack ~/.openclaw/skills/
```

### ClawHub

```bash
clawhub install pa-pack
```

## Quick Start

1. Read `PA_GUIDE.md` for the full architecture
2. Pick a component (start with `triager`)
3. Customize the prompts in `scripts/prompts/`
4. Test with your real tasks
5. Iterate

## Requirements

- Text editor (no special tools required)
- Optional: calendar API access for scheduler demos
- Optional: email access for triager/drafter demos

## License

MIT — see [LICENSE](LICENSE)

## Attribution

See [ATTRIBUTION.md](ATTRIBUTION.md) for third-party prompt research and tooling credits.
