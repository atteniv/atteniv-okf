---
type: Access Channel
title: Public REST API
description: A versioned REST API for browsing states, complexity maps, legislation, and profiles, plus authenticated grounded Q&A with cited source sections.
resource: https://nexus.atteniv.com
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

Internal design material references the API under `nexus.atteniv.app`, while
launch material uses `nexus.atteniv.com`. Confirm the canonical API hostname
before publishing externally.

# Citations

[1] [Nexus Vision API documentation (OpenAPI 3.1)](https://nexus.atteniv.com)
