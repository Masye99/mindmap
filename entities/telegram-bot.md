---
title: Telegram Bot
created: 2026-09-14
updated: 2026-09-14
type: entity
tags: [telegram, hermes, bot, setup]
sources: [raw/transcripts/session-telegram-bot-setup.md]
confidence: high
---

# Telegram Bot

Our Telegram messaging bot, connected via the Hermes gateway.

## Setup
1. Message @BotFather in Telegram -> /newbot -> pick name + username -> get token
2. `hermes gateway setup` -> select Telegram -> paste token
3. `hermes gateway start` (or `hermes gateway install` for background service)

## Capabilities
- **Voice** — voice notes transcribed, spoken replies (`/voice on`)
- **Images & files** — send/receive photos, files, reports
- **Real work** — terminal commands, web browsing, file read/write, subagents
- **Cron jobs** — scheduled tasks delivered to Telegram
- **Background sessions** — `/bg <prompt>` for long tasks

## Chat commands
| Command | Description |
|---------|-------------|
| `/new` | Start fresh conversation |
| `/model` | Swap models mid-chat |
| `/status` | Session info |
| `/sethome` | Set this chat as home channel |
| `/approve` / `/deny` | Approve/reject dangerous commands |
| `/sessions` | List/resume past sessions |

## Related
- [[hermes-agent]] — the agent framework
- [[messaging-gateway]] — the background process
