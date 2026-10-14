# MVE Agent - Turn On The Shop Lights (v1 CLI Plan)

**Company:** M.V. ELECTRONIX LLC
**Project:** MVE Agent
**Foundation:** Fork of Pi Agent (terminal coding agent with multi-provider LLM backend)

---

## Status Legend

- `[x]` Done
- `[/]` In progress
- `[ ]` Not started

---

## Phase 0: Fork and Rebrand

> Baseline: fork Pi Agent, rebrand to MVE Agent, preserve all existing AI functionality.

- [x] Fork pi-mono repository
- [x] Rename npm package to `mve-agent` (`packages/coding-agent/package.json`)
- [x] Set `piConfig.name` to `"mve-agent"` (drives `APP_NAME`, env prefix, CLI binary name)
- [x] Set `piConfig.configDir` to `".mve-agent"` (user config lives in `~/.mve-agent/agent/`)
- [x] Set `bin` entry to `"mve-agent"` for global CLI install
- [x] Update package description to `"MVE Agent workspace CLI with MVE Agent intelligence"`
- [x] Add ASCII art banner ("MVE AGENT" double-stroke) to interactive startup
- [x] Add company name "M.V. ELECTRONIX LLC" below logo in startup
- [x] Apply gold hex gradient to ASCII banner (6-color top-to-bottom)
- [x] Add "Workspace-first AI assistance powered by the MVE Agent backend." onboarding line
- [x] Update CLI help text references to use `APP_NAME` (resolves to `mve-agent`)
- [x] Verify `npm run check` passes (lint, types, shrinkwrap)
- [x] Verify `npm run build --workspace packages/coding-agent` succeeds
- [x] MVE Agent backend fully functional (chat, tools, file editing, bash, etc.)

### Phase 0 - Remaining Cleanup

- [x] Update `README.md` - remove pi.dev links, earendil-works references, pi logo
- [x] Update `README.md` - replace pi-mono repo references with MVE Agent project info
- [x] Update `package.json` `repository.url` (still points to `earendil-works/pi.git`)
- [x] Update `package.json` `author` field (still "Mario Zechner")
- [x] Review and update `CONTRIBUTING.md` for MVE Agent
- [x] Review and update `SECURITY.md` for MVE Agent
- [x] Review and update `LICENSE` attribution
- [x] Remove pi.dev domain donation section from README
- [x] Remove pi-share-hf / Hugging Face session sharing section from README (or adapt)
- [ ] Update upstream dependency package names if publishing under own scope (currently `@earendil-works/pi-*`)
- [x] Provide `mve-test.sh` / `mve-test.bat` aliases alongside `pi-test.sh` / `pi-test.bat`

---

## Phase 1: First Run Experience & CLI Onboarding

> Setup wizard for new CLI users. No API keys shipped. Safe for public GitHub.

- [x] Interactive welcome screen on first launch when no configuration exists
- [x] Provider selection prompt (OpenAI, Anthropic, Google, OpenRouter, local)
- [x] Secure API key entry prompt with masked input
- [x] Save configuration to `~/.mve-agent/agent/auth.json`
- [x] Launch interactive TUI workspace immediately after setup completes
- [x] Verify zero credentials committed to repository

---

## Phase 2: Terminal UI (TUI) & Interactive Experience

> High-performance terminal interface powered by `@earendil-works/pi-tui`.

- [x] Interactive prompt input with multi-line editing and history navigation
- [x] Differential rendering engine for flicker-free terminal updates
- [x] Gold hex gradient ASCII banner ("MVE AGENT") on startup
- [x] Status bar displaying active model, provider, thinking state, and token context
- [x] Slash command palette (`/help`, `/model`, `/clear`, `/session`, `/skills`)
- [x] Interrupt and cancellation handling (Escape, Ctrl+C)
- [x] Terminal window resize handling and reflow
- [x] Configurable keybindings via `DEFAULT_EDITOR_KEYBINDINGS` / `DEFAULT_APP_KEYBINDINGS`

---

## Phase 3: Core Agent Tools & Execution Engine

> Autonomous tools for reading, editing, and executing in the workspace.

- [x] File viewer tool with slice pagination and syntax awareness
- [x] File edit and multi-edit tools with unified diff output
- [x] Fast text search via ripgrep (`grep_search`) and directory listing (`list_dir`)
- [x] Bash command execution tool with interactive streaming and background task support
- [x] Tool execution safety gates and user approval prompts for destructive operations
- [x] Workspace boundary enforcement to keep modifications within the current project

---

## Phase 4: Multi-Provider LLM Integration

> Unified provider management via `@earendil-works/pi-ai`.

- [x] Anthropic provider support (Claude 3.5 Sonnet, Claude 3.7 Sonnet)
- [x] OpenAI provider support (GPT-4o, o1, o3-mini)
- [x] Google Gemini provider support (Gemini 2.5 Pro, Flash, Thinking)
- [x] OpenRouter and custom OpenAI-compatible endpoint support (e.g. local Ollama, vLLM)
- [x] Runtime model switching command (`/model`) without losing session state
- [x] Token usage tracking, context window limit warnings, and cost estimation
- [x] Resilient retry logic for rate limits and transient network timeouts

---

## Phase 5: Skills, Rules & Workspace Context

> Extensibility system for tailored project rules and custom tool capabilities.

- [x] Automatic rule discovery (`AGENTS.md`, `CLAUDE.md`, or workspace instruction files)
- [x] Skill system integration for modular domain capabilities
- [x] Custom system prompt configuration via `~/.mve-agent/agent/`
- [x] Session persistence, resume, and transcript management (`~/.mve-agent/agent/sessions/`)
- [x] Workspace-aware context loading without overloading token budgets

---

## Phase 6: Packaging, Distribution & Supply Chain

> Enterprise-grade supply-chain security and cross-platform installation.

- [x] Pinned external dependencies with `save-exact=true` and `min-release-age=2`
- [x] Lockfile integrity verified by pre-commit hooks (`PI_ALLOW_LOCKFILE_CHANGE=1`)
- [x] Shrinkwrap verification for published package (`packages/coding-agent/npm-shrinkwrap.json`)
- [x] Global npm distribution (`npm install -g mve-agent`)
- [x] Standalone binary compilation (Bun and Node binaries via `npm run release:local`)
- [x] Lockstep multi-package release scripts (`npm run release:patch`, `npm run release:minor`)
- [x] Cross-platform verification on Linux, macOS, and Windows

---

## Phase 7: Polish & Ship v1

> Final verification and validation for v1 CLI release.

- [ ] Interactive smoke tests in tmux (`tmux new-session -d -s mve-test "./mve-test.sh"`)
- [ ] Non-interactive headless pipe / prompt mode (`mve-agent -p "prompt"`)
- [ ] Comprehensive error messages for missing keys, network drops, and auth failures
- [ ] Full automated test suite passing via `./test.sh`
- [ ] Clean type check and lint passing via `npm run check`
- [ ] User-facing documentation and installation guide in `README.md`
- [ ] Tag v1.0.0 release

---

## v1 Success Criteria

All twelve CLI criteria must work reliably before v1 ships:

1. [x] Install MVE Agent via `npm install -g mve-agent` or standalone binary
2. [x] Interactive first-run setup wizard for provider and API key configuration
3. [x] Interactive TUI session with gold hex banner and differential rendering
4. [x] Autonomous file reading, searching, and diff-based editing
5. [x] Safe bash command execution with streaming output and user approval controls
6. [x] Multi-line prompt editing with command history navigation
7. [x] Dynamic provider and model switching at runtime (`/model`)
8. [ ] Non-interactive pipe / headless execution (`mve-agent -p "..."`)
9. [x] Session persistence, conversation history resume, and transcript logs
10. [x] Project context awareness and rule loading (`AGENTS.md`)
11. [ ] Pass `npm run check` and `./test.sh` test suite cleanly
12. [x] Resilient error recovery for API timeouts, auth errors, and rate limits

---

## Deferred (v2+ Backlog)

Explicitly out of scope for v1 CLI:

- Desktop GUI Shell (Qt / Electron / Tauri)
- Dual-pane file manager (Dolphin-style)
- Tabbed GUI code editor
- Multi-agent swarm orchestration
- Autonomous background daemon agents
- Voice interaction
- Remote workspace memory synchronization
- Cloudflare, Proxmox, and Docker dashboard integrations

---

## Architecture Notes

### Current State (CLI Architecture)

```
packages/
  coding-agent/   <-- mve-agent npm package (CLI entry point & interactive TUI)
    src/
      config.ts         APP_NAME="mve-agent", configDir=".mve-agent"
      cli.ts            CLI entry point (args parsing, modes, pipe/interactive)
      modes/interactive/ Interactive TUI (ASCII banner, gold gradient, chat loop)
    package.json        name="mve-agent", bin="mve-agent"

  agent/          <-- @earendil-works/pi-agent-core (agent runtime, tools, state)
  ai/             <-- @earendil-works/pi-ai (multi-provider LLM API)
  tui/            <-- @earendil-works/pi-tui (terminal UI library & differential renderer)
```

### Key Files for Branding & CLI Configuration

| File                                                              | What it controls                                  |
| ----------------------------------------------------------------- | ------------------------------------------------- |
| `packages/coding-agent/package.json`                              | npm name, bin, piConfig                           |
| `packages/coding-agent/src/config.ts`                             | APP_NAME, APP_TITLE, CONFIG_DIR_NAME, env prefix  |
| `packages/coding-agent/src/modes/interactive/interactive-mode.ts` | ASCII banner, company name, onboarding text       |
| `packages/coding-agent/src/cli/args.ts`                           | CLI help text and arguments                       |
| `README.md`                                                       | Project README                                    |
