# MVE Agent

MVE Agent is an AI-powered coding assistant built on the Pi Agent backend. It provides an interactive CLI for autonomous code editing, file management, and terminal command execution.

## Installation

```bash
npm install -g mve-agent
```

Or from source:

```bash
npm install --ignore-scripts
npm run build
```

## Quick Start

```bash
# Set your API key
export ANTHROPIC_API_KEY=sk-ant-...

# Run MVE Agent
mve-agent
```

Or use the interactive login:

```bash
mve-agent
/login  # Then select provider
```

MVE Agent gives the model four tools by default: `read`, `write`, `edit`, and `bash`. The model uses these to fulfill your requests. Add capabilities via skills, prompt templates, or extensions.

## Providers

MVE Agent supports multiple providers:
- Anthropic (Claude)
- OpenAI (ChatGPT, Codex)
- Google Gemini
- OpenRouter
- And many more via API keys

Use `/login` to authenticate or set environment variables.

## Features

- Interactive AI coding assistant with file editing and terminal commands
- Multi-provider LLM support
- Terminal UI with syntax highlighting
- Extensible via skills and plugins

## Documentation

See the root [README.md](../README.md) for project overview.

## License

MIT