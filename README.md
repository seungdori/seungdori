# Seunghyun

**Software architect based in South Korea — building developer tools and MCP servers for AI coding agents.**

I spend most of my time on product code, developer tools, and small systems around AI agents, market data, and frontend workflows. Lately that's mostly meant [Model Context Protocol](https://modelcontextprotocol.io) servers: three of the four projects below hand an agent structured, verifiable context instead of leaving it to guess.

**Email:** [hyun@lafi.kr](mailto:hyun@lafi.kr)

## What I Do

- **Tooling for AI agents** — MCP servers and companion skills that turn a messy domain — a design system, a live market feed, a git diff — into structured context an agent can act on. The whole protocol surface: tools, resources, prompts, and the docs the agent itself reads.
- **Real-time data systems** — long-lived WebSocket connections kept warm across multiple upstreams, ring buffers, cache layers with TTLs, bounded concurrency, REST fallback. Every response carries `source` and `age_ms`, so freshness is measured, not assumed.
- **Analysis engines** — an extensible indicator registry (73 and counting) with a Pine-syntax parser; signal evaluation run as a strictly causal event study, no look-ahead, no repaint; diff analysis across ~25 build ecosystems that emits SARIF for CI.
- **Design systems as data** — 48 styles and 57 UI-state recipes compiled into role-based tokens (JSON, CSS variables, Tailwind, TypeScript) with WCAG contrast checks, plus the production React site they live on.
- **Release engineering** — npm and PyPI packages, a GitHub Action, versioned JSON Schemas, CI with lint/type/test gates, READMEs in four languages. A tool counts as finished when someone else can install it in one command and check what it did.

## Public Work

| Project | One line | Try it |
|---|---|---|
| [web-stylebook-mcp](https://github.com/seungdori/web-stylebook-mcp) | Scored design directions, UI-state plans, and WCAG-checked tokens for coding agents | `claude mcp add web-stylebook -- npx -y web-stylebook-mcp@latest` |
| [tickscope-mcp](https://github.com/seungdori/tickscope-mcp) | Real-time crypto market data for any agent | `uvx tickscope-mcp` |
| [patchdrill](https://github.com/seungdori/patchdrill) | Deterministic proof layer for code review | `npx --yes patchdrill demo` |
| [web-stylebook](https://github.com/seungdori/web-stylebook) | 48 styles, 520 measured references, and a design-to-prompt workflow, as a live site | [webstylebook.com](https://webstylebook.com) |

### [web-stylebook-mcp](https://github.com/seungdori/web-stylebook-mcp)

[![npm](https://img.shields.io/npm/v/web-stylebook-mcp?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![downloads](https://img.shields.io/npm/dm/web-stylebook-mcp?style=flat-square&label=downloads&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook-mcp/blob/master/LICENSE)

Coding agents ship the same generic UI because they have no way to *decide* what a product should look like. This server gives them one: describe the product, tone, and density, and it returns scored style candidates with reason codes, the styles it rejected and why, UI-state plans per surface, and role-based design tokens with WCAG contrast checks. Ten tools, a catalog of 520 real-world references and 48 styles, and an audit contract that refuses to mark anything `PASS` without evidence. Deterministic, read-only, fully offline, no API key.

### [tickscope-mcp](https://github.com/seungdori/tickscope-mcp)

[![PyPI](https://img.shields.io/pypi/v/tickscope-mcp?style=flat-square&logo=pypi&logoColor=white&label=pypi&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![Python](https://img.shields.io/pypi/pyversions/tickscope-mcp?style=flat-square&logo=python&logoColor=white&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/tickscope-mcp/blob/main/LICENSE)

Live crypto market data, 73 indicators, and chart-structure recognition over MCP — no API keys. Built so agents can ask for market context without scraping around for it.

### [patchdrill](https://github.com/seungdori/patchdrill)

[![npm](https://img.shields.io/npm/v/patchdrill?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/patchdrill)
[![deterministic](https://img.shields.io/badge/deterministic-yes-2ea44f?style=flat-square)](https://github.com/seungdori/patchdrill)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/patchdrill/blob/main/LICENSE)

Reads a git diff and points out the verification that should exist before a patch is merged — no model call, no network, the same answer every time. Emits a portable Proof Pack (Markdown, JSON, SARIF, HTML) that a human, a CI gate, or a model can all inspect.

### [web-stylebook](https://github.com/seungdori/web-stylebook)

[![website](https://img.shields.io/badge/live-webstylebook.com-000000?style=flat-square)](https://webstylebook.com)
[![stars](https://img.shields.io/github/stars/seungdori/web-stylebook?style=flat-square&label=stars&color=e3b341)](https://github.com/seungdori/web-stylebook/stargazers)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook/blob/main/LICENSE)

The canonical catalog behind the MCP, published as a production React site in three languages. 32 base styles and 16 fusion styles rendered as full pages rather than thumbnails, 520 real-world references with measured color, type, spacing, and motion signals, 23 UX and 25 interface-design principles turned into observable checks, a contrast tester, a motion lab, and a prompt generator that hands all of it to an agent as one structured brief.

## How I Work

Most of what I build starts from something missing in my own workflow or an agent's; if the need is real, the tool gets finished and documented so someone else can pick it up without me. I care more about whether a system can be inspected and maintained than whether it looks clever at first glance.

## Usually Working With

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Unreal Engine](https://img.shields.io/badge/Unreal_Engine-0E1128?style=flat-square&logo=unrealengine&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-000000?style=flat-square&logo=unity&logoColor=white)
![Blender](https://img.shields.io/badge/Blender-E87D0D?style=flat-square&logo=blender&logoColor=white)

TypeScript and Python for most of the work, Rust when a hot path or a native tool needs it, and whatever else the project actually calls for. Lately that includes a game, so Unreal Engine, Unity, and Blender are on the desk as well.
