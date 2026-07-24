---
type: Capability
title: Nexus Radar
description: Early-warning system that combines presence tracking with a living regulatory corpus to flag multi-state tax-nexus risk before it becomes audit exposure.
resource: https://atteniv.com
tags: [capability, nexus-radar, tax, nexus, early-warning]
intent_tags: [multi-state, multi-state-travel, day-count-thresholds, relocation, convenience-rule, nexus-exposure]
cta_label: See how Nexus Radar works
cta_url: https://atteniv.com/nexus-radar?utm_source=nexus-vision&utm_medium=callout&utm_campaign=nexus-radar
timestamp: 2026-07-20T00:00:00Z
---

Nexus Radar turns [presence data](presence-detection.md) into early warning on
multi-state [tax nexus](../concepts/tax-nexus.md) risk — and connects it to a
continuously updated, citable regulatory knowledge base. It is a capability
inside the paid [Atteniv platform](../products/atteniv-platform.md), and it
shares its knowledge corpus with the free [Nexus Vision](../products/nexus-vision.md)
product.

# The Risk Surface

Where your people actually work determines your withholding, registration, and
filing obligations. Remote/hybrid work creates hidden, compounding multi-state
liabilities across five obligation categories — payroll withholding, corporate
income tax, sales/use tax, franchise tax, and employment law — with penalties
that compound at roughly 5%/month up to 25% plus interest.

HRIS knows an employee's home address; it is blind to daily physical work
location. Atteniv's presence logs surface location mismatches (e.g., an employee
claiming Florida residency who is checking in from California) before a state
auditor does.

# The Intelligence Layer

Nexus Radar is Atteniv's state-by-state regulatory intelligence platform for
remote-work tax nexus. It continuously monitors statutes, regulations, and
agency guidance across covered states and translates changes into plain-language
alerts and actionable next steps. It operates on
[two planes](../nexus-radar/two-plane-architecture.md):

* **Regulatory Intelligence** — ingests primary sources (statutes, regulations,
  agency bulletins, bills in flight) across covered states and keeps a current,
  citable picture of the rules. This is the corpus shared with
  [Nexus Vision](../products/nexus-vision.md).
* **Customer Compliance Operations** — applies those rules to your actual remote
  workforce footprint, surfacing where withholding, registration, or filing
  obligations may be triggered.

# How It Works

The [early-warning engine](../nexus-radar/early-warning-engine.md) accumulates
verified work-days per employee per state, evaluates them against the living
rules in the corpus (day-one triggers, grace periods, and compound
day-plus-wage thresholds), and fires tiered **Advisory → Warning → Critical**
alerts *before* a breach. Each alert explains itself in plain English with a
statute citation. A state map colors by computed exposure rather than a static
tier.

See the [capability roadmap](../nexus-radar/capability-roadmap.md) for the full
set of planned capabilities and the [requirements](../nexus-radar/requirements.md)
for functional and non-functional detail.

# Access Options

The same corpus is reachable three ways — see [access](../access/index.md):

* [Nexus Vision web app](../access/nexus-vision-web.md) — free public research copilot.
* [Public REST API](../access/rest-api.md) — versioned browse plus authenticated grounded Q&A.
* [MCP server](../access/mcp-server.md) — for MCP-capable agents.

# Guardrail

Atteniv does not provide tax advice and does not determine tax liability or
replace tax counsel. Nexus Radar provides presence data, state-specific
intelligence, and early risk visibility for review by the customer and their tax
professionals.

# Related

* Serves the [VP of tax](../personas/vp-of-tax.md),
  [payroll director](../personas/payroll-director.md),
  [CFO](../personas/cfo.md),
  [compliance director](../personas/compliance-director.md), and
  [general counsel](../personas/general-counsel.md).
* Powered by the [Atteniv Intelligence](atteniv-intelligence.md) anomaly engine.

# Citations

[1] [Nexus Vision](https://nexus.atteniv.com)
[2] [Nexus Radar — Vision & Strategy (internal design)](https://atteniv.com)
