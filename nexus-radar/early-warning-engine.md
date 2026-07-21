---
type: Architecture
title: Early-Warning Engine
description: The deterministic engine at the heart of Nexus Radar — verified presence multiplied by living rules, producing tiered cited alerts before a breach.
tags: [architecture, nexus-radar, engine, alerts, thresholds]
timestamp: 2026-07-20T00:00:00Z
---

The early-warning engine is the heart of [Nexus Radar](../capabilities/nexus-radar.md):
**verified presence × living rules → tiered, cited alerts, before a breach.** It
is deterministic and runs on cached structured data — no LLM in the hot path.
(An LLM is used only on demand, to enrich an alert's explanation.)

# Inputs and Outputs

**Inputs**

* **Presence** — resolved state, user, and check-in time from the presence log.
* **Employee baseline** — home/tax state and employment dates, plus offices.
* **Rules** — a cached projection of the corpus: day-one flag, grace-period days,
  compound wage trigger, [reciprocity](../concepts/reciprocity.md) partners, and
  [convenience-of-the-employer](../concepts/convenience-of-the-employer-rule.md)
  stance.
* **Registrations** — where the organization is registered.

**Outputs**

* Threshold-tracker rows (per employee × state × tax year).
* Alert events (Advisory / Warning / Critical), each with explanation +
  citations.
* Aggregates for the map (state coloring by computed exposure) and dashboards.

# Pipeline

1. Compute presence delta since the last run.
2. Aggregate work-days per employee × state × tax year.
3. Apply reciprocity & residency suppression (remove home-state and reciprocal
   pairs).
4. Load rules from the cached corpus projection.
5. Evaluate by rule type (day-one / grace-period / compound).
6. Compute percent-to-threshold → status + severity.
7. Upsert the threshold tracker; emit an alert event **only on status
   transition**, with a citation snapshot.

# Day Aggregation Rules

Aggregating "work days in a state" is where correctness lives:

* **Unit of presence** — one connection in a state on a calendar date = one
  work-day; de-duplicate multiple connections on the same date.
* **Home/office state** — days in the resident or assigned-office state are
  baseline and do not create nonresident nexus; tracked separately.
* **Partial/travel days** — store the raw count and apply state-specific rules;
  flag states whose rules aren't yet modeled.
* **Tax-year scoping** — thresholds reset per period (calendar year most common;
  some rolling 12-month); aggregation windows must match.
* **Non-working days** — weekends/PTO with an incidental connection should not
  count as work-days.

# Threshold Evaluation by Rule Type

| Rule type | Breach condition | "Approaching" |
|-----------|------------------|---------------|
| Day-one | first work-day in state | jumps straight to Critical on day 1 |
| Grace-period (days) | days present > grace-period days | pct ≥ warn-at (default 0.8) |
| Compound (days + wages) | both (`and`) or either (`or`) met | either component approaching |
| Economic nexus | out of scope for Tier 1 (no revenue data in core) | — |

# Severity Mapping (default; admin-configurable)

| Severity | Label | Default trigger |
|----------|-------|-----------------|
| info | Advisory | pct ≥ 0.6 and < 0.8 |
| warning | Warning | pct ≥ 0.8 and < 1.0 |
| critical | Critical | pct ≥ 1.0 (breached), day-one trigger fired, or breach with no active registration |

An event fires only on status transition to avoid alert spam.

# Reciprocity & Residency Suppression

Before evaluating a work-state rule, the engine suppresses obligations that
[reciprocity](../concepts/reciprocity.md) or residency removes — surfacing a
reciprocity *opportunity* if the org is over-withholding. Convenience-of-the-
employer aggressor states (NY/DE/PA/NE) invert the usual logic and are flagged
for a dedicated workflow rather than cleared.

# Explanation & Citations

* **Cheap path (default)** — template the explanation from cached structured
  fields and attach source citations. Zero LLM cost.
* **Rich path (on demand)** — when a user clicks "Explain," call grounded Q&A for
  a scenario-specific cited paragraph and cache it. Quota-aware; never in the
  batch loop.

Example templated explanation:

> **IL — Warning.** 4 employees have worked 26+ days in Illinois; nonresident
> withholding is required after 30 working days. Source: 35 ILCS 5/701 (via
> corpus). Registered: No → escalates to Critical on breach.

# Execution Model

* **Incremental batch** — triggered by new presence; processes only the delta.
  Target: threshold calc within ~1 minute of new location data.
* **Idempotent** — re-running over the same window must not double-emit events.
* **Per-tenant isolation** — all queries scoped by organization; RLS enforced.
* **Backfill mode** — a one-shot historical pass (retroactive nexus study) when
  an org first enables Nexus Radar.

# Edge Cases

* **VPN/egress misattribution** — IP→state can be wrong; support an HR
  confirmation step before a Critical drives action.
* **No-income-tax states** — never fire withholding alerts.
* **Unmodeled state** — mark tracker `safe` but flag `unmodeled` so it's visible,
  not silently treated as compliant.
* **Mid-year threshold change** — the tracker snapshots the rule at eval time;
  the Legislative Change Monitor surfaces the delta.

# Related

* Depends on the [two-plane architecture](two-plane-architecture.md) cache.
* Specified by [requirements](requirements.md) FR-10 through FR-22.

# Citations

[1] [Nexus Radar — Early-Warning Engine (internal design)](https://atteniv.com)
