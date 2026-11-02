# Seunghyun

**Software architect · South Korea**

I build developer tools and [Model Context Protocol](https://modelcontextprotocol.io) servers that give AI coding agents structured, verifiable context, so they decide from evidence instead of guessing. My open-source work covers UI design judgment, real-time market data, and patch verification. Each one is deterministic where it can be, installable in one command, and explicit about what it has not checked.

[![Email](https://img.shields.io/badge/hyun@lafi.kr-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:hyun@lafi.kr)

## Focus Areas

- **Agent tooling.** MCP servers and companion skills that turn a messy domain (a design system, a live market feed, a git diff) into tools, resources, and prompts an agent can act on, with output contracts it can be held to.
- **Evidence-based workflows.** Plans with stable check IDs, validators that refuse to mark work complete without matching evidence, and hash-stamped reports that a reviewer, a CI gate, or another model can verify.
- **Real-time data systems.** Long-lived WebSocket connections across multiple upstreams, ring buffers, TTL caches, bounded concurrency, and REST fallback, with the source and age of each response reported rather than assumed.
- **Release engineering.** npm and PyPI packages, a GitHub Action, versioned JSON Schemas, CI with lint, type, and test gates, and documentation in English, Korean, Japanese, and Chinese.

## Open Source

| Project | What it does | Get started |
|---|---|---|
| [web-stylebook-mcp](https://github.com/seungdori/web-stylebook-mcp) | Design judgment for coding agents, backed by before/after evidence | `claude mcp add web-stylebook -- npx -y web-stylebook-mcp@latest` |
| [patchdrill](https://github.com/seungdori/patchdrill) | Deterministic proof layer between code review and CI | `npx --yes patchdrill demo` |
| [tickscope-mcp](https://github.com/seungdori/tickscope-mcp) | Real-time crypto market data, indicators, and chart structure over MCP | `uvx tickscope-mcp` |
| [web-stylebook](https://github.com/seungdori/web-stylebook) | Design reference site and AI-ready frontend handoff | Clone, then `npm install && npm run dev` |

### [web-stylebook-mcp](https://github.com/seungdori/web-stylebook-mcp)

[![npm](https://img.shields.io/npm/v/web-stylebook-mcp?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![downloads](https://img.shields.io/npm/dm/web-stylebook-mcp?style=flat-square&label=downloads&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook-mcp/blob/master/LICENSE)

Coding agents tend to ship the same generic UI and call a critique an improvement. For an existing interface, this server drives an inspect → decide → implement → verify → report workflow: researched design foundations guide the change, the agent edits the real source, and a validator checks the before/after captures, diffs, and observed checks before anything is reported as complete. For new work it returns scored style directions with the reasons behind each rejection, page structure and product must-haves, UI-state plans, and WCAG-checked tokens or a complete `DESIGN.md`. Deterministic, read-only, offline, no API key.

### [patchdrill](https://github.com/seungdori/patchdrill)

[![npm](https://img.shields.io/npm/v/patchdrill?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/patchdrill)
[![CI](https://img.shields.io/github/actions/workflow/status/seungdori/patchdrill/ci.yml?style=flat-square&label=CI)](https://github.com/seungdori/patchdrill/actions/workflows/ci.yml)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/patchdrill/blob/main/LICENSE)

An AI reviewer says LGTM and CI is green, but the PR still shouldn't merge. PatchDrill reads the diff and reports what proof should exist before merge: leaked secrets, prompt injection in files agents read, workflow privilege escalation, source changes without tests, and lockfile drift, plus the verification commands for the changed packages across about 25 ecosystems. It runs as a CLI, a GitHub Action, or an MCP server and emits a Proof Pack (Markdown, JSON, SARIF, and an HTML dashboard). No model call, no network, the same answer every time.

### [tickscope-mcp](https://github.com/seungdori/tickscope-mcp)

[![PyPI](https://img.shields.io/pypi/v/tickscope-mcp?style=flat-square&logo=pypi&logoColor=white&label=pypi&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![Python](https://img.shields.io/pypi/pyversions/tickscope-mcp?style=flat-square&logo=python&logoColor=white&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/tickscope-mcp/blob/main/LICENSE)

A self-hostable MCP server that keeps exchange WebSocket connections warm, so an agent reads sub-second prices from a live connection instead of scraping for them. It provides 19 tools, 73 technical indicators, chart-structure recognition, and `deep_analyze`, which returns a multi-timeframe read of a symbol in a single call. No API keys.

### [web-stylebook](https://github.com/seungdori/web-stylebook)

[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook/blob/main/LICENSE)

The catalog behind the MCP server, published as a production React site in English, Korean, and Japanese. It renders 48 styles as full pages rather than thumbnails, documents 520 real-world references with measured color, type, spacing, and motion signals, and turns 23 UX and 25 interface-design principles into observable checks. A contrast tester, a motion lab, and a prompt generator package the result as one structured brief for an agent.

## Engineering Principles

- **Deterministic by default.** A tool that checks something gives the same answer for the same input. Model calls belong to the agent, not to the verifier.
- **Evidence over claims.** Missing evidence is reported as `NOT_VERIFIED`, never as `PASS`, and data carries its source and age.
- **Finished means someone else can use it.** One-command install, versioned schemas, CI gates, and documentation good enough that the project doesn't need me to explain it.

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

TypeScript and Python for most of the work, Rust when a hot path or a native tool needs it.

**Game development:**
![Unreal Engine](https://img.shields.io/badge/Unreal_Engine-0E1128?style=flat-square&logo=unrealengine&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-000000?style=flat-square&logo=unity&logoColor=white)
![Blender](https://img.shields.io/badge/Blender-E87D0D?style=flat-square&logo=blender&logoColor=white)
