<p align="center">
  <img width="200" alt="relentlessworks logo" src="https://github.com/user-attachments/assets/53604849-b3fb-4978-aa44-c11a011d9f11" />
</p>

# relentlessworks

**Agentic-first services for AI agents. The agent IS the interface.**

We build and maintain simple, headless services designed for AI agents to drive over plain HTTP. No UI, no SDK — the API is the product.

> Built with [ChatBotKit](https://chatbotkit.com) — the platform for building, deploying, and managing AI agents and agentic workflows. Follow our progress on the [ChatBotKit Hub — Coder blueprint](https://chatbotkit.com/hub/blueprints/coder).

## Philosophy

Every service we build follows these core principles:

| Principle | What it means |
|-----------|---------------|
| **Agent is the interface** | No UI, no SDK. The AI agent (ChatGPT, Claude, Cursor, etc.) is the user. The API is the product. |
| **Plain text by default** | Responses are one labeled, grepable line per record. Token-cheap and survives context truncation. JSON available on demand. |
| **Instructive errors** | Every 4xx response includes a hint telling the agent what to do next, so it can self-correct without a schema. |
| **Self-documenting** | `GET /help` (or `/.well-known/agent.md`) returns a one-page operating manual the agent loads at runtime. |
| **Simple auth** | OTP via email → long-lived bearer token. No complex OAuth flows for the basic case. |
| **Single static binary** | Go + SQLite (pure-Go, CGO_ENABLED=0), zero external dependencies, deploys as one file. |
| **Zero config defaults** | Runs out of the box. Config layered: defaults < file < env < flags. |
| **Multi-tenant ready** | Workspaces, plans, limits, audit logs built in from the start. |
| **MCP connector** | Also speaks Model Context Protocol at `/mcp` for chat client integrations. |
| **Short stable handles** | Every record is addressed by a short workspace-scoped handle (e.g. `contact_k7m2q`) that's token-cheap and easy to reference. |

## Projects

| Project | Description | Status |
|---------|-------------|--------|
| [LinkSmith](https://github.com/relentlessworks/linksmith) | Agentic-first link shortener | Active |
| [TaskPilot](https://github.com/relentlessworks/taskpilot) | Agentic-first task management | Active |
| [Notable](https://github.com/relentlessworks/notable) | Agentic-first notes & knowledge base | Active |
| [HookRelay](https://github.com/relentlessworks/hookrelay) | Agentic-first webhook relay & inspection | Active |

*More projects coming soon.*

## Tech Stack

- **Language:** Go
- **Database:** SQLite (pure-Go `modernc.org/sqlite`) — only when needed
- **Architecture:** Single binary, internal package structure, `cmd/<name>` entry points
- **Testing:** `go test ./...`, `go vet ./...`
- **Build:** Makefile-based (`make build`, `make test`, `make vet`)

## Inspired By

This approach is inspired by [crmkit](https://github.com/crmkit/crmkit) — the idea that services should be designed for agents first, not humans.

---

<p align="center">
  <sub>Built by <a href="https://github.com/relentlessworks">relentlessworks</a> with <a href="https://chatbotkit.com">ChatBotKit</a> — agentic-first, always.</sub>
</p>
