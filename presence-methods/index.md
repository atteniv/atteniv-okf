# Presence Detection Methods

Atteniv uses an **agnostic, multi-modal architecture** for
[presence detection](../capabilities/presence-detection.md): organizations pick
the method (or combination) that best fits their corporate culture and IT
infrastructure. Each method below lists how it works, its upside, and its
downside.

# Primary Pathways

* [Network Presence Detection](network-detection.md) - Flagship SIEM/firewall integration reading outbound NAT IP signals.
* [Lightweight Desktop Agent](desktop-agent.md) - Proprietary Go client deployed via MDM when log access is unavailable.
* [Badge Swipe Integration](badge-swipe.md) - Access-control and turnstile webhooks.
* [Desk Booking Integration](desk-booking.md) - Presence from hoteling / space-booking check-ins.
* [QR / Barcode Kiosks](qr-kiosk.md) - Daily-regenerated codes scanned on entry.

# Additional Methods

* [Wi-Fi Access Point Integration](wifi-access-point.md) - MAC-address presence via Wi-Fi controllers.
* [Mobile App Geofencing](mobile-geofencing.md) - Location-services check-in via a corporate mobile app.
