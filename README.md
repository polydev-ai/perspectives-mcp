# Polydev - Multi-Model AI Perspectives

**Get unstuck faster.** Query GPT 5.2, Claude Opus 4.5, Gemini 3, and Grok 4.1 simultaneously — one API call, four expert opinions.

[![npm version](https://img.shields.io/npm/v/polydev-ai.svg)](https://www.npmjs.com/package/polydev-ai)
[![SWE-bench Verified](https://img.shields.io/badge/SWE--bench-74.6%25-brightgreen)](https://polydev.ai/articles/swe-bench-paper)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## Why Polydev?

**Stop copy-pasting between ChatGPT, Claude, and Gemini.** Get all their perspectives in your IDE with one request.

| Metric | Result |
|--------|--------|
| **SWE-bench Verified** | 74.6% Resolve@2 |
| **Cost vs Claude Opus** | 62% lower |
| **Response time** | 10-40 seconds |

> *"Different models have different blind spots. Combining their perspectives eliminates yours."*

---

## Supported Models

| Model | Provider | Strengths |
|-------|----------|-----------|
| **GPT 5.2** | OpenAI | Reasoning, code generation |
| **Claude Opus 4.5** | Anthropic | Analysis, nuanced thinking |
| **Gemini 3 Pro** | Google | Multimodal, large context |
| **Grok 4.1** | xAI | Real-time knowledge, directness |

---

## Quick Start

### 1. Get your free API token

**[polydev.ai/dashboard/mcp-tokens](https://polydev.ai/dashboard/mcp-tokens)**

| Tier | Messages/Month | Price |
|------|----------------|-------|
| **Free** | 1,000 | $0 |
| **Pro** | 10,000 | $19/mo |

### 2. Install in your IDE

#### Claude Code

```bash
claude mcp add polydev -- npx -y polydev-ai@latest
```

Then set your token:
```bash
export POLYDEV_USER_TOKEN="pd_your_token_here"
```

Or add to `~/.claude.json`:

```json
{
  "mcpServers": {
    "polydev": {
      "command": "npx",
      "args": ["-y", "polydev-ai@latest"],
      "env": {
        "POLYDEV_USER_TOKEN": "pd_your_token_here"
      }
    }
  }
}
```

#### Cursor

Add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "polydev": {
      "command": "npx",
      "args": ["-y", "polydev-ai@latest"],
      "env": {
        "POLYDEV_USER_TOKEN": "pd_your_token_here"
      }
    }
  }
}
```

#### Windsurf

Add to your MCP configuration:

```json
{
  "mcpServers": {
    "polydev": {
      "command": "npx",
      "args": ["-y", "polydev-ai@latest"],
      "env": {
        "POLYDEV_USER_TOKEN": "pd_your_token_here"
      }
    }
  }
}
```

#### Cline (VS Code)

1. Open Cline settings (gear icon)
2. Go to "MCP Servers" → "Configure"
3. Add the same JSON config as above

#### OpenAI Codex CLI

Add to `~/.codex/config.toml`:

```toml
[mcp_servers.polydev]
command = "npx"
args = ["-y", "polydev-ai@latest"]

[mcp_servers.polydev.env]
POLYDEV_USER_TOKEN = "pd_your_token_here"

[mcp_servers.polydev.timeouts]
tool_timeout = 180
session_timeout = 600
```

---

## Usage

### Natural Language

Just mention "polydev" or "perspectives" in your prompt:

```
"Use polydev to debug this infinite loop"

"Get perspectives on: Should I use Redis or PostgreSQL for caching?"

"Use polydev to review this API for security issues"
```

### MCP Tool

Call the `get_perspectives` tool directly:

```typescript
{
  "tool": "get_perspectives",
  "arguments": {
    "prompt": "How should I optimize this database query?",
    "user_token": "pd_your_token_here"
  }
}
```

---

## Example Response

```
🤖 Multi-Model Analysis

┌─ GPT 5.2 ────────────────────────────────────────
│ The N+1 query pattern is causing performance issues.
│ Consider using eager loading or batch queries...
└──────────────────────────────────────────────────

┌─ Claude Opus 4.5 ────────────────────────────────
│ Looking at the execution plan, the table scan on
│ `users` suggests a missing index on `email`...
└──────────────────────────────────────────────────

┌─ Gemini 3 ───────────────────────────────────────
│ The query could benefit from denormalization for
│ this read-heavy access pattern...
└──────────────────────────────────────────────────

┌─ Grok 4.1 ───────────────────────────────────────
│ Just add an index. The real problem is you're
│ querying in a loop - fix that first.
└──────────────────────────────────────────────────

✅ Consensus: Add index on users.email, fix N+1 query
💡 Recommendation: Use eager loading with proper indexing
```

---

## Research

Our approach achieves **74.6% on SWE-bench Verified** (Resolve@2), matching Claude Opus at 62% lower cost.

| Approach | Resolution Rate | Cost/Instance |
|----------|-----------------|---------------|
| Claude Haiku (baseline) | 64.6% | $0.18 |
| + Polydev consultation | 66.6% | $0.24 |
| **Resolve@2 (best of both)** | **74.6%** | $0.37 |
| Claude Opus (reference) | 74.4% | $0.97 |

**[Read the full paper →](https://polydev.ai/articles/swe-bench-paper)**

---

## Available Tools

| Tool | Description |
|------|-------------|
| `get_perspectives` | Query multiple AI models simultaneously |
| `get_cli_status` | Check status of local CLI tools |
| `force_cli_detection` | Re-detect installed CLI tools |
| `send_cli_prompt` | Send prompts to local CLIs with fallback |

---

## Links

- **Website:** [polydev.ai](https://polydev.ai)
- **Dashboard:** [polydev.ai/dashboard](https://polydev.ai/dashboard)
- **npm:** [npmjs.com/package/polydev-ai](https://www.npmjs.com/package/polydev-ai)
- **Research:** [SWE-bench Paper](https://polydev.ai/articles/swe-bench-paper)

### IDE Guides

- [Claude Code Guide](https://polydev.ai/articles/claude-code-guide)
- [Cursor Guide](https://polydev.ai/articles/cursor-guide)
- [Cline Guide](https://polydev.ai/articles/cline-guide)
- [Codex Guide](https://polydev.ai/articles/codex-guide)

---

## License

MIT License - see [LICENSE](LICENSE) for details.

---

<p align="center">
  <b>Built by <a href="https://polydev.ai">Polydev AI</a></b><br>
  <i>Multi-model consultation for better code</i>
</p>
