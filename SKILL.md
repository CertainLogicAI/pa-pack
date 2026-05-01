# SKILL.md — pa-pack

## Name
pa-pack

## Description
A curated, opinionated stack of tools and workflows for building effective personal assistant agents. Provides modular components for triage, drafting, scheduling, and follow-up that practitioners can adapt to their own contexts.

## Version
1.0.0

## Author
CertainLogic

## License
MIT

## Category
productivity, assistant, workflow

## Tags
personal-assistant, productivity, triage, drafting, scheduling, workflow, agent-stack

## Requirements
- No hard dependencies
- Optional: calendar API (Google Calendar, Outlook)
- Optional: email API (Gmail, IMAP)

## Installation
Place the `pa-pack/` folder into your OpenClaw skills directory and restart.

## Usage

### Browse Components

```bash
openclaw skill pa-pack list
```

### Use a Component

```bash
# Generate a priority score for messages
openclaw skill pa-pack triage --input messages.json

# Draft a reply given context
openclaw skill pa-pack draft --thread thread_123 --tone concise

# Check calendar conflicts
openclaw skill pa-pack schedule --proposed "2026-06-15T10:00:00Z" --duration 60m

# Set follow-up tracking
openclaw skill pa-pack followup --deadline "2026-06-20" --topic "Contract review"
```

### Customize Prompts

Each component loads prompts from `scripts/prompts/<component>.md`. You can override these by placing a file of the same name in `~/.openclaw/skills/pa-pack/custom-prompts/`.

## Architecture

The pack follows these principles:

1. **Modularity:** Each component is self-contained. Use one, two, or all.
2. **Context-awareness:** Components expect a context object (previous messages, user preferences, time zone).
3. **Human-in-the-loop:** Outputs are suggestions, not autonomous actions. The human approves before sending.
4. **Transparency:** Every suggestion includes reasoning so the human can evaluate it.

## Component Details

### Triager
- Scores incoming messages by urgency and relevance
- Suggests action: reply now, reply later, delegate, ignore
- Requires: message subject + body + sender context

### Drafter
- Generates reply drafts given thread context and desired tone
- Supports: concise, detailed, apologetic, assertive
- Requires: thread history + intent summary

### Scheduler
- Detects conflicts with existing calendar events
- Suggests alternative slots
- Requires: proposed time + duration + attendee list

### Follow-Up
- Tracks deadlines and sends reminders
- Escalates overdue items
- Requires: deadline + topic + owner

## Limitations

- Does not have real-time calendar access unless you integrate an API
- Draft quality depends on the amount of context provided
- Triage scoring is heuristic-based, not learned from your behavior
- No persistent memory across sessions without external storage

## Changelog

### 1.0.0
- Initial release
- Triager, Drafter, Scheduler, Follow-Up components
- Prompt library with 4 tone variants
- Context-kernel pattern documentation
