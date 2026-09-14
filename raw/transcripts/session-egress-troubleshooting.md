---
source_url: "egress troubleshooting, 2026-09-14"
ingested: 2026-09-14
---

# Session: Egress proxy troubleshooting (2026-09-14)

Terminal sandbox failed with:
  "proxy.enabled is true but iron-proxy is not configured.
   Run `hermes egress setup` to mint tokens and write proxy.yaml."

Root cause: iron-proxy has no native Windows binary (v0.39.0).
Fix: `hermes egress disable` (proxy.enabled: false -> no-op).
After that, the Docker sandbox started normally.
Note: the sandbox's 9p mount of C:\ did not expose host files,
so GITHUB_TOKEN in ~/.hermes/.env was not visible inside the container.
