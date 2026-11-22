# Graph Report - flow-mcp  (2026-11-22)

## Corpus Check
- cluster-only mode — file stats not available

## Summary
- 313 nodes · 759 edges · 15 communities (13 shown, 2 thin omitted)
- Extraction: 98% EXTRACTED · 2% INFERRED · 0% AMBIGUOUS · INFERRED: 18 edges (avg confidence: 0.85)
- Token cost: 64,664 input · 206 output

## Graph Freshness
- Built from commit: `a12942d6`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- Video Assembly and Voices
- MCP Server Entry Point
- Local Core Tool Logic
- Package Manifest
- Flow UI Driver
- Remote Core Client
- Core Tool Interface
- Project Grid and Characters
- Composer Settings and Models
- Chrome Launch and Attach
- TypeScript Config
- Download Handling
- Generation and Upload
- New Tile Detection and Retry
- Agent Batch Runs

## God Nodes (most connected - your core abstractions)
1. `pause()` - 40 edges
2. `LocalCore` - 28 edges
3. `Core` - 28 edges
4. `RemoteCore` - 25 edges
5. `call()` - 23 edges
6. `runGeneration()` - 21 edges
7. `runContinue()` - 19 edges
8. `getFlowPage()` - 18 edges
9. `ensureProjectGrid()` - 17 edges
10. `scrollToTop()` - 17 edges

## Surprising Connections (you probably didn't know these)
- `RemoteCore` --implements--> `Core`  [EXTRACTED]
  src/remote.ts → src/core.ts
- `runGeneration()` --calls--> `getFlowPage()`  [EXTRACTED]
  src/flow.ts → src/chrome.ts
- `runAgentBatch()` --calls--> `getFlowPage()`  [EXTRACTED]
  src/flow.ts → src/chrome.ts
- `openProjectNav()` --calls--> `inEnglish()`  [EXTRACTED]
  src/flow.ts → src/chrome.ts
- `openOrCreateProject()` --calls--> `getFlowPage()`  [EXTRACTED]
  src/flow.ts → src/chrome.ts

## Import Cycles
- None detected.

## Communities (15 total, 2 thin omitted)

### Community 0 - "Video Assembly and Voices"
Cohesion: 0.09
Nodes (34): assemble(), AssembleOptions, ClipInfo, defaultClips(), extractAudio(), localVoices(), probe(), run (+26 more)

### Community 1 - "MCP Server Entry Point"
Cohesion: 0.08
Nodes (25): OUTPUT_ROOT, shapes, local, PATIENCE_MS, server, Task, tasks, ToolResult (+17 more)

### Community 2 - "Local Core Tool Logic"
Cohesion: 0.11
Nodes (8): jobView(), LocalCore, projectDir(), words(), characterLook(), loadLooks(), rememberCharacter(), JobQueue

### Community 3 - "Package Manifest"
Cohesion: 0.07
Nodes (30): author, bin, flow-mcp, dependencies, @modelcontextprotocol/sdk@^1.30.0, playwright-core@^1.63.0, zod@^4.6.5, description (+22 more)

### Community 4 - "Flow UI Driver"
Cohesion: 0.09
Nodes (26): attachAsset(), attachFrame(), CharacterParams, clickProjectNav(), DOWNLOAD_DIR, DownloadQuality, escapeRe(), FlowAsset (+18 more)

### Community 7 - "Project Grid and Characters"
Cohesion: 0.37
Nodes (17): getFlowPage(), createCharacter(), dismissOverlays(), downloadAsset(), editCharacter(), ensureProjectGrid(), getFlowState(), leaveCharacterEditor() (+9 more)

### Community 8 - "Composer Settings and Models"
Cohesion: 0.31
Nodes (14): applySettings(), clearBackdrops(), closeAgentSettings(), newestNanoBanana(), openSettings(), pause(), pickAgentImageModel(), pickModel() (+6 more)

### Community 9 - "Chrome Launch and Attach"
Cohesion: 0.23
Nodes (10): CDP_PORT, cdpUp(), CHROME_PATHS, ensureEnglish(), FLOW_URL, getBrowser(), inEnglish(), launchChrome() (+2 more)

### Community 10 - "TypeScript Config"
Cohesion: 0.18
Nodes (10): compilerOptions, module, moduleResolution, outDir, rootDir, skipLibCheck, strict, target (+2 more)

### Community 11 - "Download Handling"
Cohesion: 0.42
Nodes (10): downloadScene(), downloadsNow(), downloadTile(), extensionOf(), moveFile(), savePortrait(), unpackTakes(), useOwnDownloadDir() (+2 more)

### Community 12 - "Generation and Upload"
Cohesion: 0.32
Nodes (8): agentToggle(), downloadMedia(), mediaTile(), runGeneration(), tileByIdOrTitle(), typePrompt(), uploadAsset(), waitForUpload()

### Community 13 - "New Tile Detection and Retry"
Cohesion: 0.29
Nodes (8): freshMedia(), hoverTile(), newErrorTiles(), renameTile(), retryableErrorTile(), retryErrorTile(), retryNewErrorTiles(), waitForNewMedia()

### Community 14 - "Agent Batch Runs"
Cohesion: 0.60
Nodes (5): agentRound(), closeAgentSession(), mediaIds(), runAgentBatch(), step()

## Knowledge Gaps
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Core` connect `Core Tool Interface` to `Video Assembly and Voices`, `MCP Server Entry Point`, `Local Core Tool Logic`, `Remote Core Client`?**
  _High betweenness centrality (0.157) - this node is a cross-community bridge._
- **Should `Video Assembly and Voices` be split into smaller, more focused modules?**
  _Cohesion score 0.08776595744680851 - nodes in this community are weakly interconnected._
- **Why does `RemoteCore` connect `Remote Core Client` to `MCP Server Entry Point`, `Core Tool Interface`?**
  _High betweenness centrality (0.104) - this node is a cross-community bridge._
- **Should `MCP Server Entry Point` be split into smaller, more focused modules?**
  _Cohesion score 0.0761904761904762 - nodes in this community are weakly interconnected._
- **Why does `LocalCore` connect `Local Core Tool Logic` to `Video Assembly and Voices`, `Chrome Launch and Attach`, `Core Tool Interface`, `MCP Server Entry Point`?**
  _High betweenness centrality (0.088) - this node is a cross-community bridge._
- **Should `Local Core Tool Logic` be split into smaller, more focused modules?**
  _Cohesion score 0.10952380952380952 - nodes in this community are weakly interconnected._
- **Should `Package Manifest` be split into smaller, more focused modules?**
  _Cohesion score 0.07007575757575757 - nodes in this community are weakly interconnected._