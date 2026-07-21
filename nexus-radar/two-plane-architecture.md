---
type: Architecture
title: Two-Plane Architecture
description: The organizing principle behind Nexus Radar — a regulatory-intelligence plane and a customer-compliance-ops plane, joined by a PII-free server-to-server seam.
tags: [architecture, nexus-radar, design, corpus, integration]
timestamp: 2026-07-20T00:00:00Z
---

Nexus Radar is organized as **two planes** that are joined but never merged.
This is the discipline that keeps the shared regulatory corpus authoritative
while keeping customer data private.

# The Two Planes

* **Regulatory-intelligence plane** — the [Nexus Vision](../products/nexus-vision.md)
  corpus. The source of truth for every rule, threshold, reciprocity fact, and
  citation. It is *never duplicated into* the core application.
* **Customer-compliance-ops plane** — the Atteniv core database. The source of
  truth for this organization's employees, presence days, registrations,
  alerts, and documents. It *never leaves* core.

# The Seam

The two planes are joined by the [public API](../access/rest-api.md) /
[MCP server](../access/mcp-server.md), called **server-to-server**. Core sends
**abstracted scenarios** (e.g., "resident of NJ, 15 days in ME, $4k sourced") —
**never employee PII**.

# The Key Discipline

The split forces two rules that keep the system correct and affordable:

* **Structured/cached corpus data drives bulk computation** — threshold math over
  thousands of employee-days runs against a cached projection of the corpus.
* **LLM Q&A endpoints drive on-demand explanation only** — they are quota-limited
  and never called in a loop.

# What Each Side Has

**Core** (the verified *where*): a presence engine that resolves every employee
connection to a US state via network egress, plus organization registration
records. See [presence detection](../capabilities/presence-detection.md).

**Nexus Vision** (the cited *so what*): a grounded, cited regulatory corpus;
state profiles for all 50 states + DC with complexity buckets
(baseline / guardrail / red_flag / no_income_tax), scored dimensions, and curated
properties; legislation with full text and AI interpretations; and single- and
multi-state cited Q&A.

# What We Deliberately Do NOT Do

* Not re-ingesting the corpus into core — cache projections; call live for
  Q&A/legislation.
* Not hardcoding rules in core — if a rule isn't in the corpus, that's a corpus
  gap to close, not a constant to add.
* Not sending employee PII across the seam — abstracted scenarios only.
* Not calling LLM Q&A in bulk loops — bulk math uses cached structured data.

# Related

* [Early-warning engine](early-warning-engine.md) consumes the cached corpus
  projection.
* [Requirements](requirements.md) FR-1 through FR-7 specify the seam and
  source-of-truth behavior.

# Citations

[1] [Nexus Radar — Vision & Strategy (internal design)](https://atteniv.com)
