---
type: Capability
title: Presence Detection
description: Non-intrusive detection of actual physical office presence using existing endpoint security infrastructure.
tags: [capability, presence, pillar-1, network, privacy-first]
timestamp: 2026-07-20T00:00:00Z
---

**Strategic Pillar I.** Presence Detection is the foundation of the
[Atteniv platform](../products/atteniv-platform.md) — the single signal that
powers compliance, office optimization, and Nexus Radar.

# What It Does

Detects actual physical office presence using existing endpoint security
infrastructure — **not** badge swipes, cameras, or new software. A device
connected to the office network means the employee is physically in the office.

The Presence Detection Engine continuously correlates three inputs into an
audit-ready record of where each employee is actually working — by day, by
office, by jurisdiction:

* Network-level presence (outbound NAT IP signals and device connections)
* SSO / SAML session corroboration
* Badge check-ins

# How It Works

The flagship method analyzes outbound NAT IP signals on the corporate network:
when an employee's egress IP matches the IPs associated with a specific office
location, that employee is counted as present. A lightweight optional client is
available for environments where API access to security logs is restricted.

Atteniv is deliberately **agnostic** about the detection method — organizations
choose the method or combination that fits their security posture and IT stack.
See [presence methods](../presence-methods/index.md) for all supported pathways,
including [network detection](../presence-methods/network-detection.md),
[the desktop agent](../presence-methods/desktop-agent.md),
[badge swipe](../presence-methods/badge-swipe.md),
[desk booking](../presence-methods/desk-booking.md),
[QR kiosks](../presence-methods/qr-kiosk.md),
[Wi-Fi access points](../presence-methods/wifi-access-point.md), and
[mobile geofencing](../presence-methods/mobile-geofencing.md).

# What It Is Not

This is **presence confirmation, not surveillance**:

* No keystroke logging.
* No screen capture.
* No monitoring of work output or application usage.

# Why It Matters

Traditional approaches fail: badge data is gameable via
[coffee badging](../concepts/coffee-badging.md), and HRIS location fields are
self-reported and stale. Non-intrusive network detection is frictionless and
privacy-first — the presence signal is what makes
[compliance automation](compliance-automation.md),
[office optimization](office-optimization.md), and
[Nexus Radar](nexus-radar.md) possible.

# Integrations

Integrates with endpoint security vendors including Zscaler, Fortinet, Check
Point Harmony, and Microsoft Endpoint Defender. See
[endpoint security integrations](../integrations/endpoint-security.md).

# Citations

[1] [Atteniv platform overview](https://atteniv.com)
