# Hydracept agent plugins

Hydracept gives game teams production-ready assets through one API. Every job leaves a receipt.

A Zencode product · © Zencode Consulting Inc. · MIT License

Version `0.1.3` (marketplace `distributionVersion`, independent of the Python SDK).

This public repo is the **Cursor / Claude / MCP catalog**. Cursor Marketplace review should use `.cursor-plugin/marketplace.json` and `plugins/cursor`.

## Cursor Marketplace

Plugin path: `plugins/cursor`

1. Install **Hydracept** from the Cursor Marketplace (or enable this repository as a plugin catalog).
2. Open **Plugins → Configure** and set `HYDRACEPT_API_KEY`. Get a key at [hydracept.com/start](https://hydracept.com/start). Do not paste the key into chat.
3. The plugin talks to hosted MCP at `https://api.hydracept.com/mcp` with `Authorization: Bearer ${HYDRACEPT_API_KEY}`.

Included for Cursor:

- Hosted MCP (`mcp.json`) — no stdio fallback, no secrets in git
- Skills: `hydracept`, `hydracept-setup`, `hydracept-image`, `hydracept-sheet`, `hydracept-smoke`
- Commands: `/hydracept-init`, `/hydracept-doctor`
- Rule: never solicit API keys in chat

## Claude Code

```text
/plugin marketplace add hydracept/agent-plugins
/plugin install hydracept@hydracept
```

When Claude prompts for plugin configuration, set `HYDRACEPT_API_KEY`. Claude substitutes `${user_config.HYDRACEPT_API_KEY}` (not Cursor's `${HYDRACEPT_API_KEY}`).

## MCP Registry

Remote server `com.hydracept/mcp` at `https://api.hydracept.com/mcp`.

## Security

This repository contains **no API keys or tokens**. Secrets are collected by the host (Cursor variables / Claude `userConfig`) and sent only as the Authorization header to Hydracept.

## CLI fallback

```bash
pip install hydracept
python -m hydracept agents install --auto
```
