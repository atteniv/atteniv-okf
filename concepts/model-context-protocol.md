---
type: Concept
title: Model Context Protocol (MCP)
description: An open protocol for connecting AI agents to external tools and data sources, used to expose the Nexus corpus to agents.
tags: [concept, mcp, agent, integration, glossary]
timestamp: 2026-07-20T00:00:00Z
---

The **Model Context Protocol (MCP)** is an open protocol for connecting AI agents
to external tools and data sources through a standard interface, so any
MCP-capable client can consume a server's capabilities with a single config
block.

# Why It Matters to Atteniv

Atteniv ships an [`atteniv-nexus` MCP server](../access/mcp-server.md) that
exposes the Nexus corpus — state browsing, legislation, and grounded cited Q&A —
to agents like Claude and Cursor. The same MCP is mounted server-side into the
[Atteniv platform](../products/atteniv-platform.md)'s AI chat to power
footprint-aware answers.

# Citations

[1] [Nexus Vision — API and developer access](https://nexus.atteniv.com)
