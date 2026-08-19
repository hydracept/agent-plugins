# Hydracept for Claude

AI execution you can trust: routed jobs, pinned inference, receipts, BYOK, and game-asset workflows (transparent PNGs, Sheet & Slice) through one API.

A Zencode product · © Zencode Consulting Inc.

Add the Hydracept marketplace, then install the namespaced plugin:

```text
/plugin marketplace add hydracept/agent-plugins
/plugin install hydracept@hydracept
```

When Claude prompts for plugin configuration, set `HYDRACEPT_API_KEY` (Claude `userConfig`). The plugin sends `Authorization: Bearer ${user_config.HYDRACEPT_API_KEY}`. Do not paste the key into chat.

Commands: `/hydracept-init`, `/hydracept-doctor`.

Local CLI fallback (optional): `python -m hydracept agents install --auto`.
