# Seunghyun

**Software architect based in South Korea — building developer tools and MCP servers for AI coding agents.**

I spend most of my time on product code, developer tools, and small systems around AI agents, market data, and frontend workflows. Lately that's mostly meant [Model Context Protocol](https://modelcontextprotocol.io) servers: three of the four projects below hand an agent structured, verifiable context instead of leaving it to guess.

## What I Do

- **Tooling for AI agents** — MCP servers and companion skills that turn a messy domain — a design system, a live market feed, a git diff — into structured context an agent can act on. The whole protocol surface: tools, resources, prompts, and the docs the agent itself reads.
- **Real-time data systems** — long-lived WebSocket connections kept warm across multiple upstreams, ring buffers, cache layers with TTLs, bounded concurrency, REST fallback. Every response carries `source` and `age_ms`, so freshness is measured, not assumed.
- **Analysis engines** — an extensible indicator registry (73 and counting) with a Pine-syntax parser; signal evaluation run as a strictly causal event study, no look-ahead, no repaint; diff analysis across ~25 build ecosystems that emits SARIF for CI.
- **Design systems as data** — 48 styles and 57 UI-state recipes compiled into role-based tokens (JSON, CSS variables, Tailwind, TypeScript) with WCAG contrast checks, plus the production React site they live on.
- **Release engineering** — npm and PyPI packages, a GitHub Action, versioned JSON Schemas, CI with lint/type/test gates, READMEs in four languages. A tool counts as finished when someone else can install it in one command and check what it did.

## Public Work

### [web-stylebook-mcp](https://github.com/seungdori/web-stylebook-mcp) — design intelligence for AI coding agents

[![npm](https://img.shields.io/npm/v/web-stylebook-mcp?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![downloads](https://img.shields.io/npm/dm/web-stylebook-mcp?style=flat-square&label=downloads&color=cb3837)](https://www.npmjs.com/package/web-stylebook-mcp)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook-mcp/blob/master/LICENSE)

An MCP server that hands the agent scored design *contracts* — visual directions, UI-state plans, and WCAG-checked design tokens — so it builds from evidence instead of defaulting to hero + three cards. Deterministic, read-only, fully local, no API key, and it ships with a companion skill.

### [Tickscope MCP](https://github.com/seungdori/tickscope-mcp) — real-time crypto market data for any agent

[![PyPI](https://img.shields.io/pypi/v/tickscope-mcp?style=flat-square&logo=pypi&logoColor=white&label=pypi&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![Python](https://img.shields.io/pypi/pyversions/tickscope-mcp?style=flat-square&logo=python&logoColor=white&color=3776AB)](https://pypi.org/project/tickscope-mcp/)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/tickscope-mcp/blob/main/LICENSE)

An MCP server for live crypto market data, 73 indicators, and chart-structure recognition — no API keys. Built so agents can ask for market context without scraping around for it.

### [PatchDrill](https://github.com/seungdori/patchdrill) — the deterministic proof layer for code review

[![npm](https://img.shields.io/npm/v/patchdrill?style=flat-square&logo=npm&label=npm&color=cb3837)](https://www.npmjs.com/package/patchdrill)
[![deterministic](https://img.shields.io/badge/deterministic-yes-2ea44f?style=flat-square)](https://github.com/seungdori/patchdrill)
[![MCP](https://img.shields.io/badge/MCP-server-6E56CF?style=flat-square)](https://modelcontextprotocol.io)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/patchdrill/blob/main/LICENSE)

Reads a git diff and points out the verification that should exist before a patch is merged — no model call, no network, the same answer every time. Emits a portable Proof Pack (Markdown, JSON, SARIF, HTML) that a human, a CI gate, or a model can all inspect.

### [Web Stylebook](https://github.com/seungdori/web-stylebook) — the style catalog behind the MCP, as a live site

[![website](https://img.shields.io/badge/live-webstylebook.com-000000?style=flat-square)](https://webstylebook.com)
[![stars](https://img.shields.io/github/stars/seungdori/web-stylebook?style=flat-square&label=stars&color=e3b341)](https://github.com/seungdori/web-stylebook/stargazers)
[![license](https://img.shields.io/badge/license-MIT-3b82f6?style=flat-square)](https://github.com/seungdori/web-stylebook/blob/main/LICENSE)

48 style references, side-by-side comparison, prompt workflows, and a motion lab — the curated catalog that `web-stylebook-mcp` draws from.

## How I Work

Most of what I build starts from a concrete need — something missing in my own workflow or an agent's. If the need is real, the tool gets built, finished, and documented so someone else can pick it up without me.

I like software that is easy to inspect: clear inputs, clear outputs, tests that mean something, and docs that stay close to the code. I care more about whether a system can be checked and maintained than whether it looks clever at first glance.

## Usually Working With

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

TypeScript and Python for most of the work, Rust when a hot path or a native tool needs it, and whatever else the project actually calls for.
