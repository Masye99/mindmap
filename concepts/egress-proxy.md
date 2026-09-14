---
title: Egress Proxy (iron-proxy)
created: 2026-09-14
updated: 2026-09-14
type: concept
tags: [proxy, docker, hermes, troubleshooting]
sources: [raw/transcripts/session-egress-troubleshooting.md]
confidence: high
---

# Egress Proxy (iron-proxy)

A TLS-intercepting proxy that swaps opaque proxy tokens for real upstream API
credentials at the network boundary, so sandboxes never hold real keys.

## How it works
- Docker sandbox sends CONNECT/HTTP forward to iron-proxy (host:9090)
- iron-proxy mints a leaf cert from its CA, matching the proxy token
- It swaps the secret for the real upstream key (OpenRouter, OpenAI, etc.)
- Sandboxes only ever see proxy tokens + CA cert

## Commands
```
hermes egress install      # download the pinned binary
hermes egress setup        # wizard: CA, mappings, proxy.yaml
hermes egress start        # spawn the proxy daemon
hermes egress status       # binary + config + pid + listening state
hermes egress disable      # flip proxy.enabled = false
```

## Windows gotcha (v0.39.0)
iron-proxy does **not** ship native Windows binaries. It must run on
Linux/macOS/WSL. On a Windows host, the clean fix is to disable it:
```
hermes egress disable
```
This makes the feature a complete no-op — the Docker sandbox starts normally
and reads real credentials directly from `~/.hermes/.env`.

## Related
- [[hermes-agent]] — the agent framework
- [[telegram-bot]] — where we hit the proxy error during setup
