---
name: hydracept-doctor
description: Check Hydracept connection, capabilities, and local CLI readiness.
---

# Hydracept doctor

Inspect whether this workspace can use Hydracept. Do not submit paid jobs.

## Hosted MCP (marketplace plugin)

1. Call MCP `hydracept_status`. Report connected vs authentication required.
2. If unauthenticated, tell the human to set `HYDRACEPT_API_KEY` in the plugin configuration (Cursor: **Plugins → Configure**; Claude: plugin `userConfig`) or run `/hydracept-init`.
3. Call MCP `hydracept_capabilities` and report a short list of capability keys.
4. Stop. Do not call `hydracept_smoke` unless the human explicitly asks.

## CLI fallback

If the Hydracept CLI is installed:

```bash
python -m hydracept doctor
python -m hydracept agent-status --json
```

If the CLI is missing, say so and continue with MCP-only diagnosis. Do not install packages unless the human approves.

## Safety

- Never print API keys, bearer tokens, or `.env` values
- Use capability keys (`image.generate.v1`), not provider model names
