---
type: Presence Method
title: Lightweight Desktop Agent (Go Client)
description: A proprietary, lightweight Go client deployed via MDM that detects office presence by matching the device's public NAT IP to known office IPs.
tags: [presence-method, agent, go, mdm, endpoint]
timestamp: 2026-07-20T00:00:00Z
---

For organizations unable to provide direct firewall or SIEM log access, Atteniv
offers a proprietary, **lightweight Go client** that can be deployed via MDM to
employee laptops (Windows or Mac). It is the fallback for
[network presence detection](network-detection.md).

# How It Works

Running quietly in the background, the client detects when the user's public NAT
IP address changes and matches it against Atteniv's database of known office IP
addresses.

# The Upside

Highly accurate, and bypasses complex backend network integrations.

# The Downside

Requires IT to package and deploy software directly onto employee devices.

# Citations

[1] [Determining Office Presence — Atteniv's agnostic approach (internal)](https://atteniv.com)
