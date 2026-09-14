---
title: Messaging Gateway
created: 2026-09-14
updated: 2026-09-14
type: concept
tags: [hermes, gateway, automation]
sources: [raw/transcripts/session-telegram-bot-setup.md]
confidence: high
---

# Messaging Gateway

The single background process that connects all configured chat platforms to
the agent. It handles sessions, runs cron jobs, and delivers voice messages.

## Architecture
- Platform adapters (Telegram, Discord, Slack, WhatsApp, ...) receive messages
- Per-chat session store routes each conversation
- Messages dispatch to the AIAgent for processing
- Cron scheduler ticks every 60s to execute due jobs

## Commands
```
hermes gateway              # run in foreground
hermes gateway setup        # interactive platform configuration
hermes gateway install      # install as a background service
hermes gateway start/stop   # manage the service
hermes gateway status       # check status
```

## Platforms
Telegram, Discord, Slack, WhatsApp, Signal, SMS, Email, Home Assistant,
Mattermost, Matrix, DingTalk, Feishu/Lark, WeCom, Weixin, iMessage, QQ,
Teams, LINE, ntfy, and more.

## Related
- [[telegram-bot]] — our Telegram setup
- [[hermes-agent]] — the agent framework
