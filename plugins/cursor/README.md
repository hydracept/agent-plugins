# Hydracept for Cursor

AI execution you can trust: routed jobs, pinned inference, receipts, BYOK, and game-asset workflows (transparent PNGs, Sheet & Slice) through one API.

A Zencode product · © Zencode Consulting Inc.

Install from the Cursor Marketplace, or clone `https://github.com/hydracept/agent-plugins` and enable the Cursor plugin under `plugins/cursor`.

Set `HYDRACEPT_API_KEY` in **Plugins → Configure**. The plugin sends `Authorization: Bearer ${HYDRACEPT_API_KEY}` to https://api.hydracept.com/mcp.

Commands: `/hydracept-init`, `/hydracept-doctor`.

Local CLI fallback (optional): `python -m hydracept agents install --auto`.
