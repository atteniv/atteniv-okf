---
type: Presence Method
title: Access Control & Badge Swipe Integration
description: Integration with existing physical security and turnstile systems, which pass a webhook or log to Atteniv on badge swipe.
tags: [presence-method, badge, access-control, webhook]
timestamp: 2026-07-20T00:00:00Z
---

The most common traditional method for tracking attendance: integrating with
existing physical security and turnstile systems.

# How It Works

When an employee swipes their badge to unlock a door, the access-control system
securely passes a webhook or log to Atteniv.

# The Upside

Leverages existing physical security infrastructure with no changes to the
employee's routine.

# The Downside

Vulnerable to [coffee badging](../concepts/coffee-badging.md) — an employee
swipes in just to be seen and leaves immediately — unless the organization also
strictly monitors swipe-out times for duration tracking. This gameability is a
core reason Atteniv leads with
[network presence detection](network-detection.md) instead.

# Citations

[1] [Determining Office Presence — Atteniv's agnostic approach (internal)](https://atteniv.com)
