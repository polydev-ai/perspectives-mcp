# perspectives-mcp

MCP server for multi-model AI perspectives - query GPT-4, Claude, Gemini, and Grok in parallel.

[![npm version](https://img.shields.io/npm/v/polydev-ai.svg)](https://www.npmjs.com/package/polydev-ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## What it does

When you need a second opinion on code, architecture decisions, or debugging - Polydev queries multiple AI models simultaneously and returns their diverse perspectives. Think of it as a panel of AI experts at your fingertips.

**Supported models:**
- GPT-4 (OpenAI)
- - Claude (Anthropic)
  - - Gemini (Google)
    - - Grok (xAI)
     
      - ## Quick Start
     
      - ### 1. Get your API token
     
      - Get a free token at [polydev.ai/dashboard/mcp-tokens](https://polydev.ai/dashboard/mcp-tokens)
     
      - Free tier: 1,000 messages/month
     
      - ### 2. Install in your IDE
     
      - #### Claude Code
     
      - Add to `~/.claude/config.json`:
     
      - ```json
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

        #### Cline (VS Code Extension)

        1. Open Cline settings (gear icon)
        2. 2. Go to "MCP Servers" > "Configure"
           3. 3. Add the same JSON config as above
             
              4. #### Windsurf
             
              5. Add to your MCP configuration:
             
              6. ```json
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

                 ## Usage

                 Just mention "polydev" or "perspectives" in your prompt:

                 ```
                 "Use polydev to debug this infinite loop"
                 "Get perspectives on: Redis vs PostgreSQL for caching?"
                 "Use polydev to review this API for security issues"
                 ```

                 ## Response time

                 10-40 seconds (queries multiple AI APIs in parallel)

                 ## Links

                 - [Website](https://polydev.ai)
                 - - [npm package](https://www.npmjs.com/package/polydev-ai)
                   - - [Cursor Guide](https://polydev.ai/articles/cursor-guide)
                     - - [Cline Guide](https://polydev.ai/articles/cline-guide)
                       - - [Codex Guide](https://polydev.ai/articles/codex-guide)
                        
                         - ## License
                        
                         - MIT
