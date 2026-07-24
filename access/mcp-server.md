---
type: Access Channel
title: MCP Server
description: A Model Context Protocol server that drops Nexus Radar into Claude, Cursor, or any MCP-capable agent with a single config block.
tags: [access, mcp, agent, claude, cursor]
timestamp: 2026-07-20T00:00:00Z
---

The `atteniv-nexus` MCP server exposes the Nexus corpus to
[Model Context Protocol](../concepts/model-context-protocol.md)-capable agents —
Claude, Cursor, or any other — with a single config block.

# Endpoint

`https://nexus.atteniv.app/api/mcp` — a stateless streamable-HTTP endpoint,
authenticated with an API token (`nxs_live_…`).

# What It Enables

* Browse states, complexity map, state profiles, and legislation.
* Ask single-state and multi-state grounded, cited tax-nexus questions.
* Manage chat conversations.

Inside the [Atteniv platform](../products/atteniv-platform.md), this same MCP is
mounted server-side into core's AI chat (roadmap Tier 2.1 / FR-30), giving
footprint-aware grounded answers.

# Citations

[1] [Nexus Vision — API and developer access](https://nexus.atteniv.app/developers)
