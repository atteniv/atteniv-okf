---
type: Integration
title: Endpoint Security Integrations
description: Presence-detection sources — endpoint security and network vendors Atteniv reads to confirm physical office presence.
tags: [integration, endpoint-security, presence, network]
timestamp: 2026-07-20T00:00:00Z
---

These vendors are the source signal for
[network presence detection](../presence-methods/network-detection.md) and
[Wi-Fi access point detection](../presence-methods/wifi-access-point.md). Atteniv
reads NAT IP / MAC signals via API — it does not add surveillance software.

# Supported Tools

| Vendor | Role |
|--------|------|
| Zscaler | Cloud security proxy — outbound NAT IP signal |
| Fortinet | Firewall / SIEM logs |
| Check Point Harmony | Endpoint security logs |
| Microsoft Endpoint Defender | Endpoint / device connection signal |
| Cisco Meraki | Wi-Fi controller — MAC-address presence and stay duration |

For environments where API access to these logs is restricted, the
[lightweight desktop agent](../presence-methods/desktop-agent.md) is the
fallback.

# Citations

[1] [Atteniv platform overview](https://atteniv.com)
