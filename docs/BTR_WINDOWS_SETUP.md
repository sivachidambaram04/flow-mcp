# Born to Represent: Windows setup

How this fork runs on the BTR production PC (Windows 10), so it can be rebuilt from scratch.
Upstream: https://github.com/GTAI-1/flow-mcp. No code changes yet; this file records the local setup only.

## Requirements found on the PC

- Node.js v24.21.0, git 2.55.0, Google Chrome (C:\Program Files\Google\Chrome)
- Power settings: screen and sleep set to Never (Flow needs the PC awake while it generates)

## Folders

| What | Where |
| --- | --- |
| Program (this repo) | `D:\BTR_Works\flow-mcp` |
| Generated stills and clips | `D:\BTR_Works\flow-mcp-out` (set by `FLOW_MCP_OUTPUT`) |
| Chrome profile with the Google sign-in | `C:\Users\Admin\.flow-mcp` (default `FLOW_MCP_HOME`) |

Keep everything out of folders OneDrive syncs.

## Install

```powershell
cd D:\BTR_Works
git clone https://github.com/sivachidambaram04/flow-mcp
cd flow-mcp
npm install
npm run build
npm run login   # sign in to Google yourself in the window that opens (a separate account, not the main one)
```

Then open or create a project in the Flow window (e.g. "BTR 17th Oct") and leave the window open.

## Register with Claude

The `claude` CLI is not installed on this PC, so the server is added directly to `C:\Users\Admin\.claude.json`
under `mcpServers` (back the file up first), then Claude is fully restarted:

```json
"flow": {
  "type": "stdio",
  "command": "node",
  "args": ["D:/BTR_Works/flow-mcp/dist/index.js"],
  "env": { "FLOW_MCP_OUTPUT": "D:/BTR_Works/flow-mcp-out" }
}
```

## Trial results (17 Oct 2026, free plan, 50 credits a day)

- Still, Nano Banana, 9:16 (768x1376): 0 credits, about 70 s
- Clip, Omni 1.1 Flash, 8 s 720p 9:16, first frame from the still: 12 credits, about 100 s, no visible watermark
- Prompting note: "slow push-in" moved a long way; write "very subtle slow push-in" for gentle moves
- Windows: install, build, login, status, image and video generation, and downloads all worked with no flow-mcp errors
