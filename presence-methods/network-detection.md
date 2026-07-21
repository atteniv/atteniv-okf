---
type: Presence Method
title: Network Presence Detection (SIEM / Firewall)
description: The flagship, privacy-first method — analyze firewall logs to match an employee's outbound NAT IP to a corporate office location.
tags: [presence-method, network, siem, firewall, flagship, privacy-first]
timestamp: 2026-07-20T00:00:00Z
---

The flagship [presence detection](../capabilities/presence-detection.md)
approach. It leverages the endpoint security infrastructure an organization
already has in place, integrating via API with leading security vendors such as
Zscaler, Fortinet, Check Point Harmony, or Microsoft Defender. See
[endpoint security integrations](../integrations/endpoint-security.md).

# How It Works

Atteniv analyzes firewall logs to identify when an employee's outbound NAT IP
address matches the IP addresses associated with a specific corporate office
location. A device connected to the office network means the employee is
physically in the office.

# The Upside

Frictionless and "privacy-first": requires no new hardware and avoids the "Big
Brother" feel of invasive surveillance.

# The Downside

Highly regulated InfoSec teams may initially be reluctant to provide API access
to these logs.

# Fallback

For organizations that cannot provide log access, the
[lightweight desktop agent](desktop-agent.md) achieves the same result at the
endpoint.

# Citations

[1] [Determining Office Presence — Atteniv's agnostic approach (internal)](https://atteniv.com)
