---
type: Architecture
title: Nexus Radar Requirements
description: Functional and non-functional requirements and user stories by persona for the Nexus Radar corpus-integration work.
tags: [architecture, nexus-radar, requirements, user-stories]
timestamp: 2026-07-20T00:00:00Z
---

Requirement IDs are stable references. Priority: **P0** (must, gates the tier),
**P1** (should), **P2** (nice). Each maps back to a tier in the
[capability roadmap](capability-roadmap.md).

# Functional Requirements

## Tier 0 — Seam & Source of Truth

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-1 | Core authenticates to the Nexus Vision public API with a machine-scoped service credential, server-side only. | P0 |
| FR-2 | A nightly job syncs all 50+DC state profiles + complexity buckets into the regulatory cache. | P0 |
| FR-3 | All regulatory facts shown in core read from the cache, not a hardcoded states table. | P0 |
| FR-4 | The hardcoded states table is retired after dual-read parity is verified. | P0 |
| FR-5 | Every regulatory fact displayed carries a source citation and a "last verified" timestamp. | P1 |
| FR-6 | If the corpus is unreachable, core serves the last cached projection with a freshness warning. | P0 |
| FR-7 | Corpus response payloads are validated at the boundary before entering core. | P0 |

## Tier 1 — Early-Warning Engine

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-10 | Aggregate verified work-days per employee × state × tax year, de-duplicated per calendar date. | P0 |
| FR-11 | Home/resident-state and reciprocal-pair days are suppressed from nonresident evaluation. | P0 |
| FR-12 | Evaluate day-one, grace-period, and compound (days + wages) rule types from the cache. | P0 |
| FR-13 | Emit tiered alerts (Advisory / Warning / Critical) on status transition only. | P0 |
| FR-14 | Alert severity thresholds are admin-configurable per org, with sensible defaults. | P1 |
| FR-15 | Each alert includes a plain-English explanation and citation snapshot. | P0 |
| FR-16 | Each alert records the exact triggering rule values at fire time (audit snapshot). | P0 |
| FR-17 | The map colors states by computed exposure blended with complexity bucket. | P0 |
| FR-18 | Per-state drill-down shows employee roster, day-counts, status, registration, rule + citation. | P0 |
| FR-19 | Dashboard top-line metrics: Active Jurisdictions, Approaching Nexus, Employees Out-of-State. | P1 |
| FR-20 | A backfill mode runs a retroactive pass over historical presence on first enablement. | P1 |
| FR-21 | Registration-gap detector flags "nexus without registration" and the inverse. | P1 |
| FR-22 | Unmodeled states/rules are flagged visibly, never silently treated as compliant. | P0 |

## Tier 2 — Conversational Advisor

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-30 | The MCP is mounted into core's AI chat, server-side. | P1 |
| FR-31 | Grounded answers inject the org's footprint context and remain state-cited. | P1 |
| FR-32 | Alerts, state panels, and employee rows expose an "Explain / Ask about this" affordance. | P1 |
| FR-33 | Per-employee cited narratives are generated from abstracted scenarios (no PII across the seam). | P1 |
| FR-34 | Q&A affordances show a coverage badge; non-live states fall back or hide the affordance. | P0 |
| FR-35 | Every grounded answer is persisted with its citations and a scenario hash. | P1 |
| FR-36 | Per-tenant quota metering wraps all Q&A calls; corpus 429 degrades gracefully. | P0 |

## Tier 3 & 4 — Proactive and Forward-Looking

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-40 | A poller detects new/changed legislation in footprint states and emits scoped impact briefs. | P1 |
| FR-41 | Impact briefs are plain-English and name the affected employee count/scope. | P1 |
| FR-42 | A weekly digest summarizes new nexus, approaching thresholds, changes, and reciprocity. | P2 |
| FR-43 | Reciprocity navigator surfaces over-withholding on actual pairs; flags expired agreements. | P1 |
| FR-44 | A board/M&A-ready cited compliance summary can be generated on demand. | P2 |
| FR-50 | Pre-hire/relocation what-if previews new obligations for a prospective home+work state. | P2 |
| FR-51 | Employee self-service explainer of their own multi-state situation, with disclaimers. | P2 |

# Non-Functional Requirements

| ID | Requirement | Target |
|----|-------------|--------|
| NFR-1 | Threshold calculation latency after new presence data | < 1 minute |
| NFR-2 | Nexus Radar dashboard load | < 3 seconds |
| NFR-3 | No PII crosses the seam | Enforced by abstracted-scenario contract |
| NFR-4 | All corpus calls server-side; service token never reaches the browser | Absolute |
| NFR-5 | Alerts + Q&A answers retained with immutable audit trail | 7 years (tax audit statute) |
| NFR-6 | Bulk paths never call LLM Q&A | Architectural invariant |
| NFR-7 | Per-tenant isolation on all engine + cache reads | RLS enforced |
| NFR-8 | Graceful degradation on corpus 401/403/429/5xx | No user-facing crash |
| NFR-9 | Regulatory facts trace to a corpus citation + version | 100% of displayed facts |
| NFR-10 | "Not tax advice" disclaimer on every generated answer | Absolute |

# User Stories by Persona

* **[VP of Tax](../personas/vp-of-tax.md)** — see active vs. approaching nexus
  at a glance (US-1); every alert cites its statute (US-2); be told when a law
  changes where we have people (US-3).
* **[Payroll Director](../personas/payroll-director.md)** — drill into a state to
  see which employees drive exposure (US-4); be warned *before* a threshold is
  crossed (US-5); know where we over-withhold due to reciprocity (US-6).
* **[CFO](../personas/cfo.md)** — a single dashboard of total exposure for board
  and M&A (US-7); an on-demand cited compliance summary for diligence (US-8).
* **[HR Manager](../personas/hr-operations.md)** — ask plain-English questions
  grounded in our footprint (US-9); a pre-hire nexus check (US-10).
* **[General Counsel](../personas/general-counsel.md)** — every alert and answer
  carries an immutable, cited audit trail (US-11).
* **[Employee](../personas/employee.md)** — a plain-English explanation of my
  multi-state situation (US-12).

# Citations

[1] [Nexus Radar — Requirements (internal design)](https://atteniv.com)
