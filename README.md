<div align="center">
  <h1>AEI — Autonomous Engineering Intelligence</h1>
  <p><b>Let AI agents do the engineering work. You stay in control.</b></p>
</div>

---

AEI is a commercial desktop and server platform that puts AI agents to work on your codebase. Describe an objective in plain English — AEI plans it, executes it, verifies it, and delivers auditable results. It runs entirely on your own hardware or private VPS, using the AI providers you already subscribe to.

No third-party agent cloud. No code sent anywhere you haven't configured. No black box.

---

## Core Capabilities

### Autonomous Task Execution
Describe what you want built, fixed, or changed. AEI assigns the task, plans the steps, runs commands against your workspace, streams progress live, and surfaces results as verifiable artifacts — with a complete timeline of every step, every command, and every file touched. Tasks are queued, prioritised, and run with configurable concurrency.

### Multi-Agent Collaborative Pipelines
Complex objectives get broken into a coordinated pipeline of specialised agents. Each agent hands context forward to the next. If a stage fails, the system can self-heal — automatically queuing a recovery agent and continuing the run without losing the overall goal.

### Universal Model Gateway
Connect any major AI provider using your own API keys and subscriptions. AEI supports OpenAI, Anthropic, Google Gemini, Azure OpenAI, and custom endpoints out of the box. Route different tasks to different models, define a model catalogue, and override routing per task type. If one provider is unavailable, routing falls back automatically. Your credentials stay local — nothing is relayed through AEI's infrastructure.

### Browser Automation
Agents can navigate URLs, take full-page screenshots, click elements, and fill forms using a built-in headless browser service. Useful for UI verification, scraping reference content, or automating web-based workflows as part of a larger task pipeline.

### Workspace & File Operations
Agents operate directly on your filesystem within boundaries you define. Every file change is proposed as a reviewable edit before it is applied — showing the diff, the affected path, and the agent's reasoning. Edits can be applied, rejected, or reverted. Full audit trail included.

### Persistent Knowledge & Memory
AEI maintains a persistent knowledge store backed by PostgreSQL with vector search. Agents can write verified facts during a run and recall relevant context in future runs — without re-reading your entire codebase each time. Knowledge entries carry confidence scores and verification flags.

### Plugin System
Extend AEI with plugins that contribute additional models, agent templates, or tools. Import a plugin from a URL or register one locally. Each plugin is health-checked on install and periodically thereafter. Plugins can be enabled, disabled, updated, or removed without restarting the system.

### Live Streaming Interface
Every token from the model streams directly into the chat console as it arrives. Events, task state, and artifacts update in real time without polling. The interface separates the live agent console from the structured task timeline and artifact viewer.

### MCP Server Integration
AEI exposes its task management, workspace operations, and knowledge store through a Model Context Protocol server over SSE transport — allowing external agents and LLM tools to interact with a running AEI instance programmatically.

### Reliability Diagnostics
A built-in reliability system runs automated checks against the live deployment:
- **Restore drills** — spins up a real task, verifies it completes, confirms recovery works
- **Replay consistency** — verifies a replayed task produces consistent results
- **Recovery smoke tests** — confirms the system recovers cleanly from unexpected restarts
- **Reliability gates** — a dashboard of pass/warn/fail indicators across all subsystems
- **Reliability history** — exportable report of all checks run over time

These run on demand or on a schedule and surface issues before they affect production work.

---

## Deployment Options

### Desktop Application
AEI ships as a native desktop app for Windows, macOS, and Linux via Tauri. The app starts the orchestrator automatically on launch and shows a single integrated window. No separate server process to manage.

### Self-Hosted Server (Docker)
Run AEI on any Linux machine or VPS with Docker installed. A single `docker compose up` starts the full stack: web UI, orchestrator, browser service, and PostgreSQL. Services are health-checked and restart automatically.

### VPS Deployment with Built-In Tooling
AEI includes deployment scripts for pushing to any remote VPS over SSH — syncing code, managing environment files, and operating the Docker stack remotely. Access the running deployment from a local browser via an included SSH tunnel helper. Compatible with any VPS provider, including Ionos, Hetzner, DigitalOcean, Linode, OVH, Vultr, and others.

### Public Access via Tunnel
For access from outside your local network without opening inbound ports, AEI supports tunnel-based public access. The included tunnel profile works with any compatible tunnel service — Cloudflare Tunnel, Ngrok, and similar providers are all supported. Set your tunnel token and deploy with the tunnel flag.

---

## Infrastructure

| Component | Technology |
|---|---|
| Desktop shell | Tauri (Rust) |
| Orchestrator | Node.js |
| Web UI | Node.js static server |
| Browser automation | Playwright (Chromium headless) |
| Database | PostgreSQL 15+ with pgvector |
| Containers | Docker Compose |
| Public access | Tunnel service (user-provided) |
| Deployment tooling | PowerShell + SSH |

---

## Security

AEI is designed for single-owner, self-hosted deployment.

- The orchestrator refuses to start without an API token set
- All write operations require a valid bearer token
- Agent command execution is restricted to an explicit allowlist of command prefixes
- File operations are restricted to configured workspace root paths
- Plugin imports are validated — HTTPS required, private/loopback addresses blocked
- All credentials are managed via environment variables, never stored in application code

---

## Future Implementations & Work in Progress

This section tracks capabilities currently in development or planned for upcoming releases.

### In Progress
- **Windows-native path handling** — full support for Windows workspace paths without manual configuration
- **Non-streaming model console output** — displaying task results in the live console for providers that do not support token streaming
- **Model selection persistence** — remembering your last-used model selection across sessions

### Planned
- **Multi-user support** — shared deployments with per-user permissions and isolated workspaces
- **Agent-to-agent direct messaging** — agents communicating and delegating to each other via MCP without routing through the orchestrator
- **Automatic provider failover** — seamless fallback to a secondary provider when a primary key is exhausted or rate-limited
- **Rate limiting on task creation** — protecting self-hosted deployments from runaway task queues
- **Built-in diff viewer** — inline before/after comparison of proposed file edits directly in the UI
- **Scheduled tasks** — cron-style task scheduling without external tooling
- **Extended plugin marketplace** — community-sourced plugins discoverable and installable from a central directory

### Under Consideration
- **Local model support** — routing tasks to locally-hosted models via Ollama or compatible runtimes
- **Mobile companion interface** — read-only monitoring of running tasks and reliability status from mobile
- **Webhook notifications** — push task completion and failure events to Slack, Discord, or custom endpoints

---

*This section is updated with each release. Features listed here are subject to change in scope or priority.*

---

## Licensing & Availability

AEI is **proprietary software**. It is not open source and is not available for contribution or redistribution.

To acquire a licence, contact: **bob@bobswan.uk**

---

*AEI is an independent product. It is not affiliated with Google, Anthropic, OpenAI, or Microsoft.*
