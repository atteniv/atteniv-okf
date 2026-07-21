---
type: Presence Method
title: Wi-Fi Access Point Integration
description: Passive presence detection by checking whether an employee's registered MAC address is connected to a corporate Wi-Fi controller.
tags: [presence-method, wifi, mac-address, meraki]
timestamp: 2026-07-20T00:00:00Z
---

Similar to [network presence detection](network-detection.md), this method
integrates directly with local Wi-Fi controllers such as Cisco Meraki (already
an Atteniv integration partner). See
[endpoint security integrations](../integrations/endpoint-security.md).

# How It Works

The system checks whether an employee's registered MAC address (laptop or
corporate mobile phone) is currently connected to the access point.

# The Upside

Passive, highly accurate, and excellent for tracking the *duration* of an
employee's stay — which combats [coffee badging](../concepts/coffee-badging.md).

# The Downside

Employees must ensure their Wi-Fi is on and connected to the correct corporate
network to be counted.

# Citations

[1] [Determining Office Presence — Atteniv's agnostic approach (internal)](https://atteniv.com)
