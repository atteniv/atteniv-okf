---
type: Persona
title: Payroll Director
description: Runs multi-state withholding; needs to adjust withholding before the payroll cycle and catch over-withholding.
tags: [persona, payroll, withholding, reciprocity]
timestamp: 2026-07-20T00:00:00Z
---

The Payroll Director manages multi-state withholding, SUI, and registrations.

# What They Need

* Drill into a state and see which employees drive the exposure, to adjust
  withholding before the payroll cycle. *(US-4)*
* Be warned *before* an employee crosses a threshold, not after. *(US-5)*
* Know where the company is over-withholding due to
  [reciprocity](../concepts/reciprocity.md), so it can stop. *(US-6)*

# How Atteniv Serves Them

Per-state drill-down (FR-18), transition-based tiered alerts
([early-warning engine](../nexus-radar/early-warning-engine.md)), and the
Reciprocity & Safe Harbor Navigator (roadmap Tier 3.2).

# Citations

[1] [Nexus Radar — Requirements (internal design)](https://atteniv.com)
