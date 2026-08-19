---
name: hydracept-init
description: Bootstrap Hydracept in this project using hosted MCP or the CLI init flow.
---

# Hydracept init

Bootstrap Hydracept without asking the human to paste secrets into chat.

## Preferred path (marketplace / hosted MCP)

1. Confirm the Hydracept plugin is enabled and the `hydracept` MCP server is connected.
2. If Cursor asks for plugin variables, have the human set `HYDRACEPT_API_KEY` in **Plugins → Configure**. Do not solicit the key in chat.
3. Call MCP `hydracept_status` (or the hosted equivalent) to confirm authentication.
4. Call MCP `hydracept_capabilities` and summarize available capability keys.
5. Offer `/hydracept-smoke` only when the human explicitly wants a paid verification job.

## CLI fallback

Use this when hosted MCP is not configured or the human already uses the Hydracept CLI:

1. Check `python -m hydracept --help`. If missing, explain `pip install hydracept` and wait for approval.
2. Run `python -m hydracept init --apply --yes --json`.
3. If status is `interaction_required`, present `action.url` and wait for the human to finish the browser connect flow, then run `python -m hydracept init --apply --yes --json --wait`.
4. Unattended / CI: `HYDRACEPT_API_KEY` plus `init --apply --yes --json` or `--ci`.

## Safety

- Never ask the user to paste API keys in chat
- Never echo secrets from terminal output into chat
- Prefer MCP tools over reimplementing HTTP
