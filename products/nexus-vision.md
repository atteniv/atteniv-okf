---
type: Product
title: Nexus Vision
description: Free, public, citation-backed Q&A service explaining how all 50 states and DC tax remote and nonresident employees.
resource: https://nexus.atteniv.com
tags: [product, nexus-vision, tax, remote-work, public, free]
timestamp: 2026-07-20T00:00:00Z
---

Nexus Vision is a **free, publicly available intelligence service** that gives
payroll, HR, and finance professionals grounded, citation-backed answers to one
of the hardest questions in the hybrid-work era: **how each U.S. state taxes the
wages of remote and nonresident employees.** It launched in July 2026 and is
available on the web and via an API for integrators.

It covers how states handle income-tax withholding, how nonresident wages are
sourced (including the [convenience-of-the-employer rule](../concepts/convenience-of-the-employer-rule.md)),
[reciprocity agreements](../concepts/reciprocity.md), de-minimis thresholds and
grace periods, and local or city wage taxes — across all 50 states and the
District of Columbia.

# The Problem It Addresses

Remote and hybrid work made employee location flexible; state payroll,
withholding, and [nexus](../concepts/tax-nexus.md) rules did not become simple
because work became flexible. The hard question is no longer "Where does this
employee live?" but "**Where did work actually happen, which state rules apply,
and can we prove what we knew at the time?**"

This is not one national rule — it is a state-by-state problem, made harder by
[convenience-of-the-employer rules](../concepts/convenience-of-the-employer-rule.md)
and record-keeping requirements (e.g., Pennsylvania's demand for "adequate
current records" of nonresident-source compensation).

# What It Does

Unlike a static FAQ or a search engine, Nexus Vision answers **real
situations**. A user can ask about a single state or describe a scenario in
plain language — for example, a Colorado company whose employee works remotely
from Colorado but spends three months a year in California. Nexus Vision
identifies the states involved and returns a single synthesized answer that
reasons across each state's rules plus the cross-state principles that tie them
together — residency, credit for taxes paid to another state, day-based
sourcing, and [reciprocity](../concepts/reciprocity.md) — with citations to the
underlying statutes.

For each covered jurisdiction, Nexus Vision provides:

* **Linked statute and guidance views** — the underlying law, with key
  provisions tagged to topics like payroll withholding, employer registration,
  convenience-of-the-employer, and mobile workforce.
* **Plain-English summaries** — concise explanations of what a rule means
  operationally, written for HR and payroll audiences.
* **Natural-language Q&A over the corpus** — ask questions in plain English and
  get a grounded answer that cites the exact sections it relies on.
* **Complexity ratings** — a color-coded posture map classifying states as
  *no income tax*, *baseline*, *guardrail*, or *red-flag*.

# Example Questions It Answers

* What counts as New York-source income for a nonresident?
* What is the "convenience of the employer" rule, and which states apply it?
* How many days can an employee work in another state before triggering nexus?
* What is the employer's liability if withholding was missed?
* Can a single remote employee create corporate income tax nexus for our
  business in their state?

# Relationship to Nexus Radar

The same nexus knowledge corpus that powers Nexus Vision also drives
[Nexus Radar](../capabilities/nexus-radar.md) inside the paid
[Atteniv platform](atteniv-platform.md):

* **Nexus Vision** is the *free, public research layer*.
* **Nexus Radar** is the *proactive, paid platform feature* that connects
  presence data to nexus risk.

See [two-plane architecture](../nexus-radar/two-plane-architecture.md) for how
the shared corpus is structured.

# How to Access It

* [Nexus Vision web app](../access/nexus-vision-web.md) — the free research copilot.
* [Public REST API](../access/rest-api.md) — versioned browse plus authenticated grounded Q&A.
* [MCP server](../access/mcp-server.md) — drop the corpus into any MCP-capable agent.

# Guardrail

Nexus Vision is honest about where a situation calls for professional advice.
Atteniv does not provide tax advice, determine tax liability, or replace tax
counsel.

# Citations

[1] [Nexus Vision](https://nexus.atteniv.com)
[2] [Atteniv launch announcement — Nexus Vision](https://atteniv.com)
