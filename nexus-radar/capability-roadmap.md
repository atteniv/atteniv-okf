---
type: Architecture
title: Nexus Radar Capability Roadmap
description: Tiered idea catalog for Nexus Radar, from foundational plumbing through the conversational advisor, proactive monitoring, and forward-looking features.
tags: [architecture, nexus-radar, roadmap, planning]
timestamp: 2026-07-20T00:00:00Z
---

The Nexus Radar roadmap is organized into five tiers, foundational →
forward-looking. Each phase is independently shippable; the ordering matters
more than dates. Effort is rough T-shirt sizing.

# Tier 0 — Foundational Plumbing

Everything rides on this.

* **0.1 Retire the hardcoded states table** — make the corpus the regulatory
  source of truth; nightly-sync a projection of state profiles. Corpus
  authoritative; core caches. *(Effort: M.)*
* **0.2 Citation + freshness everywhere** — every threshold/fact core displays
  carries a source link into the corpus legislation and a "last verified" date.
  *(Effort: S.)*

# Tier 1 — The Early-Warning Engine

The actual Nexus Radar. See the [early-warning engine](early-warning-engine.md).

* **1.1 Presence × living rules → tiered alerts** — the highest-value single
  item. *(Effort: L.)*
* **1.2 Every alert explains itself, with a citation.** *(Effort: S given 1.1.)*
* **1.3 Registration gap detector** — computed nexus vs. registrations.
  *(Effort: S.)*

# Tier 2 — Conversational & Advisory

The Natural Language Tax Advisor.

* **2.1 Footprint-aware grounded chat** — mount the MCP into core's chat;
  answers are cited and specific to the org's data. *(Effort: M.)*
* **2.2 "Explain this" / "Ask about this state" affordances.** *(Effort: S given 2.1.)*
* **2.3 Per-employee cited exposure narrative** — abstracted scenario in, cited
  plain-English story out. *(Effort: M.)*

# Tier 3 — Proactive Monitoring

The compounding moat.

* **3.1 Footprint-scoped Legislative Change Monitor** — poll corpus legislation
  for the org's footprint states; generate scoped impact briefs ("NE LB1023
  signed — affects your 14 employees with NE presence"). Highest-differentiation
  item; corpus side ~80% built. *(Effort: M.)*
* **3.2 Reciprocity & Safe Harbor Navigator** — overlay
  [reciprocity](../concepts/reciprocity.md) onto actual home→work pairs; surface
  over-withholding and flag expired agreements. *(Effort: M.)*
* **3.3 Board-ready compliance digest** — periodic cited posture summary for
  CFO/M&A readiness. *(Effort: M.)*

# Tier 4 — Forward-Looking

* **4.1 Pre-hire / relocation nexus check** — "Candidate will work from Austin,
  home state OK → new obligations?" Extends to the What-If Scenario Modeler.
  *(Effort: M.)*
* **4.2 Employee self-service explainer** — plain-English "here's your
  multi-state situation"; kills the #1 payroll ticket. *(Effort: M–L.)*

# Roadmap Mapping

| Roadmap capability | This design |
|--------------------|-------------|
| Nexus Radar (Foundation, "LIVE") | Rebuilt properly as Tier 1 |
| Nexus Exposure Map (Building) | Tier 1 map coloring by computed exposure |
| Natural Language Tax Advisor (Next) | Tier 2 |
| Legislative Change Monitor (Next) | Tier 3.1 |
| Reciprocity & Safe Harbor Navigator (Next) | Tier 3.2 |
| What-If Scenario Modeler (Planned) | Tier 4.1 |
| Employee Tax Impact Dashboard (Future) | Tier 4.2 |

# If Only Two Things Ship

**1.1** makes Nexus Radar real; **3.1** is the moat (and is mostly already built
on the corpus side).

# Deliberately Out of Scope

Wage Allocator / payroll write-back, Compliance Vault / COE Defense Builder,
sales/use economic-nexus, and international Permanent Establishment monitoring
remain on the roadmap but are later than the corpus-integration work above.

# Citations

[1] [Nexus Radar — Vision & Strategy (internal design)](https://atteniv.com)
