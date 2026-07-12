# MVE Agent - Turn On The Shop Lights (v1 Plan)

**Company:** M.V. ELECTRONIX LLC
**Project:** MVE Agent
**Foundation:** Fork of Pi Agent (preserving AI backend)

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

- [ ] Update `README.md` - remove pi.dev links, earendil-works references, pi logo
- [ ] Update `README.md` - replace pi-mono repo references with MVE Agent project info
- [ ] Update `package.json` `repository.url` (still points to `earendil-works/pi.git`)
- [ ] Update `package.json` `author` field (still "Mario Zechner")
- [ ] Review and update `CONTRIBUTING.md` for MVE Agent
- [ ] Review and update `SECURITY.md` for MVE Agent
- [ ] Review and update `LICENSE` attribution
- [ ] Remove pi.dev domain donation section from README
- [ ] Remove pi-share-hf / Hugging Face session sharing section from README (or adapt)
- [ ] Update upstream dependency package names if publishing under own scope (currently `@earendil-works/pi-*`)

---

## Phase 1: First Run Experience

> Setup wizard for new users. No API keys shipped. Safe for public GitHub.

- [ ] Welcome screen on first launch (no existing config detected)
- [ ] Provider selection prompt (OpenAI, Anthropic, Google, OpenRouter, local)
- [ ] API key entry prompt
- [ ] Save configuration to `~/.mve-agent/agent/auth.json`
- [ ] Launch workspace after setup completes
- [ ] Verify no credentials exist in repository

---

## Phase 2: Desktop GUI Shell (Qt / Electron / Tauri)

> Wrap the CLI agent inside a native desktop application with panel layout.

### 2A: Technology Decision

- [ ] Evaluate Qt vs Electron vs Tauri for cross-platform desktop shell
- [ ] Decide on framework (user plan recommends Qt)
- [ ] Scaffold project structure for desktop app
- [ ] Wire `mve-agent` CLI backend into desktop process

### 2B: Workspace Layout

- [ ] Implement main window with panel layout
- [ ] File Browser A panel (left, upper)
- [ ] Editor panel (center)
- [ ] AI Chat panel (right)
- [ ] File Browser B panel (bottom-left or full-width)
- [ ] Terminal A panel (bottom-left)
- [ ] Terminal B panel (bottom-right)
- [ ] Panel resizing (drag borders)
- [ ] Panel collapse/expand
- [ ] Panel drag-and-dock to new locations
- [ ] Layout presets: Default, Developer, Sysadmin, AI Assistant
- [ ] Custom layout save/load
- [ ] Remember last-used layout on startup

---

## Phase 3: File Browser (Dolphin-style)

> Dual-pane file manager integrated into workspace.

- [ ] Dual file panes (A and B)
- [ ] Folder tree with expand/collapse
- [ ] File list view with icons
- [ ] File previews
- [ ] File/folder selection
- [ ] New file
- [ ] New folder
- [ ] Rename
- [ ] Delete
- [ ] Copy
- [ ] Move
- [ ] Drag and drop between panes
- [ ] Refresh
- [ ] Sync Mode: selecting a folder updates active project, AI context, and terminal cwd

---

## Phase 4: Built-in Editor

> Tabbed code editor with syntax highlighting.

- [ ] Tabbed interface (multiple files open)
- [ ] Syntax highlighting for: HTML, CSS, JS, TS, JSON, YAML, Markdown, Python, Shell, Dockerfile, text
- [ ] Line numbers
- [ ] Search (Ctrl+F / Cmd+F)
- [ ] Find and replace
- [ ] Auto-save option
- [ ] Manual save (Ctrl+S / Cmd+S)
- [ ] Dark theme integration
- [ ] Editor tab synced with AI context (AI knows active file)

---

## Phase 5: Integrated Terminal

> Real terminal emulator (not simulated), sharing workspace context.

- [ ] Embedded terminal emulator (xterm.js or equivalent)
- [ ] Split-pane terminals (A and B)
- [ ] Multiple sessions
- [ ] Copy and paste
- [ ] Scrollback buffer
- [ ] Resizable panes
- [ ] Terminal cwd synced with workspace (File Browser Sync Mode)

---

## Phase 6: AI Chat Panel

> MVE Agent backend surfaced in a GUI chat panel.

- [ ] Chat message display (user + assistant)
- [ ] Text input with submit
- [ ] Streaming responses
- [ ] Project awareness (current folder, selected file, active tab)
- [ ] File editing by AI reflected in editor
- [ ] Command suggestions from AI executable in terminal
- [ ] Code generation responses
- [ ] Refactoring assistance

---

## Phase 7: Settings UI

> GUI settings panel for provider and model management.

- [ ] Add provider (OpenAI, Anthropic, Google, OpenRouter, local)
- [ ] Remove provider
- [ ] Change active provider
- [ ] Manage API keys (add, edit, delete)
- [ ] Change model
- [ ] Settings persisted to `~/.mve-agent/agent/`

---

## Phase 8: Installation and Distribution

> `npm install -g mve-agent` must work end to end.

- [ ] Verify global npm install works on Linux
- [ ] Verify global npm install works on macOS
- [ ] Verify global npm install works on Windows
- [ ] `mve-agent` command launches application
- [ ] Desktop shortcut / .desktop file generation (Linux)
- [ ] Cross-platform startup confirmed

---

## Phase 9: Polish and Ship v1

> Final pass before declaring "shop lights are on."

- [ ] Professional dark theme across all panels
- [ ] Consistent branding (MVE Agent, M.V. ELECTRONIX LLC)
- [ ] Error handling for missing providers / invalid keys
- [ ] Smoke test all 12 success criteria (see below)
- [ ] Write user-facing README for installation and usage
- [ ] Tag v1.0.0 release

---

## v1 Success Criteria

All twelve must work reliably before v1 ships:

1. [ ] Install MVE Agent with npm
2. [ ] Configure provider settings
3. [ ] Browse files
4. [ ] Open projects
5. [ ] Edit files
6. [ ] Use syntax highlighting
7. [ ] Use split file panes
8. [ ] Use split terminal panes
9. [ ] Chat with AI
10. [ ] Allow AI to edit files
11. [ ] Allow AI to execute commands
12. [ ] Maintain project context automatically

---

## Deferred (v2+ Backlog)

Do not build until v1 ships:

- Multi-agent systems
- Autonomous agents
- Docker dashboards
- Proxmox dashboards
- Cloudflare dashboards
- Team collaboration
- Voice interaction
- Mobile apps
- Plugin marketplace
- Remote workspaces
- Memory synchronization

---

## Architecture Notes

### Current State (Post-Rebrand)

```
packages/
  coding-agent/   <-- mve-agent npm package (CLI entry point)
    src/
      config.ts         APP_NAME="mve-agent", configDir=".mve-agent"
      cli.ts            CLI entry point
      modes/interactive/ Interactive TUI (ASCII banner, keybindings, chat)
    package.json        name="mve-agent", bin="mve-agent"

  agent/            <-- @earendil-works/pi-agent-core (runtime, tools, state)
  ai/               <-- @earendil-works/pi-ai (multi-provider LLM API)
  tui/              <-- @earendil-works/pi-tui (terminal UI library)
```

### Key Files for Branding

| File                                                              | What it controls                                  |
| ----------------------------------------------------------------- | ------------------------------------------------- |
| `packages/coding-agent/package.json`                              | npm name, bin, piConfig                           |
| `packages/coding-agent/src/config.ts`                             | APP_NAME, APP_TITLE, CONFIG_DIR_NAME, env prefix  |
| `packages/coding-agent/src/modes/interactive/interactive-mode.ts` | ASCII banner, company name, onboarding text       |
| `packages/coding-agent/src/cli/args.ts`                           | CLI help text                                     |
| `README.md`                                                       | Project README (still has upstream pi references) |
