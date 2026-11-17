---
title: Bulk cargo bookings are here
type: added
hidden: false
published_at: '2026-11-17T15:00:00.000Z'
author: Andrew Erdman
---
You can now book **bulk cargo** as well as satellites. Set `payload.type` to `bulk_cargo` and tell us whether it needs a pressurized hold:

```json
{
  "launch_id": "lch_7Hq2Zr",
  "payload": { "type": "bulk_cargo", "name": "Hydroponics resupply", "mass_kg": 820, "pressurized": true }
}
```

See [Book a launch slot](/docs/book-a-launch-slot) for the full flow, or try it in the [API Reference](/reference/createbooking).
