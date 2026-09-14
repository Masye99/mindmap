---
title: Hermes Agent
created: 2026-09-14
updated: 2026-09-14
type: entity
tags: [hermes, setup, reference]
sources: [raw/transcripts/session-telegram-bot-setup.md]
confidence: high
---

# Hermes Agent

Hermes Agent is an open-source AI agent framework by Nous Research. It runs in
the terminal, a native desktop app, messaging platforms, and IDEs.

## What we set up
- **Desktop app** — the chat surface we use (Electron, native)
- **Telegram bot** — messaging gateway connecting Telegram to the agent
- **Cron jobs** — scheduled tasks (e.g. bills & renewals reminder)
- **Skills** — procedural memory for recurring task types

## Key paths
```
~/.hermes/config.yaml       Main configuration
~/.hermes/.env              API keys and secrets
~/.hermes/skills/           Installed skills
~/.hermes/state.db          Session store (SQLite + FTS5)
~/.hermes/sessions/         Gateway routing index
```

## Related
- [[telegram-bot]] — our Telegram messaging setup
- [[messaging-gateway]] — the background process
- [[egress-proxy]] — sandbox credential isolation
