---
type: Access Channel
title: Public REST API
description: A versioned REST API for browsing states, complexity maps, legislation, and profiles, plus authenticated grounded Q&A with cited source sections.
resource: https://nexus.atteniv.app
tags: [access, api, rest, openapi, integration]
timestamp: 2026-07-20T00:00:00Z
---

The public REST API lets integrators bring Nexus answers into their own tools and
workflows. It is described by an OpenAPI 3.1 specification and is the
server-to-server [seam](../nexus-radar/two-plane-architecture.md) that
[Nexus Radar](../capabilities/nexus-radar.md) calls.

# What It Provides

* **Versioned browse (public)** — states, complexity map, legislation, and state
  profiles.
* **Authenticated grounded Q&A** — single- and multi-state cited answers, plus
  chat conversation management.

# Security Posture

JWT-enforced and **fail-closed**. All corpus calls are server-side; the service
token never reaches the browser (NFR-4). Per-tenant quota metering wraps Q&A
calls, and a corpus `429` degrades gracefully (FR-36, NFR-8).

# Note on URL

The API and developer portal are served from `nexus.atteniv.app`; the
user-facing Nexus Vision site is `nexus.atteniv.com`.

# Citations

[1] [Nexus Vision API documentation (OpenAPI 3.1)](https://nexus.atteniv.app/developers)
