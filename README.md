# Hydracept agent plugins

AI execution infrastructure for games and agent-built software.

A Zencode product · © Zencode Consulting Inc.

Version `0.1.1` (marketplace `distributionVersion`, independent of the Python SDK).

## Cursor

Install **Hydracept** from the Cursor Marketplace, or use this repository as a Cursor plugin catalog (`.cursor-plugin/marketplace.json`).

Set `HYDRACEPT_API_KEY` in **Plugins → Configure**.

## Claude Code

```text
/plugin marketplace add hydracept/agent-plugins
/plugin install hydracept@hydracept
```

When Claude prompts for plugin configuration, set `HYDRACEPT_API_KEY`. Claude substitutes `${user_config.HYDRACEPT_API_KEY}` (not Cursor's `${HYDRACEPT_API_KEY}`).

## MCP Registry

Remote server `com.hydracept/mcp` at `https://api.hydracept.com/mcp`.

## CLI fallback

```bash
pip install hydracept
python -m hydracept agents install --auto
```
