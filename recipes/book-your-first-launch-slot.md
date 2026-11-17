---
title: Book your first launch slot
description: Find a launch with room for your payload and reserve it, in about 20 lines.
hidden: false
recipe:
  color: '#2F7BF5'
  icon: 🚀
---
```javascript Node.js
const BASE = 'https://api.us-east.orbit.erdman.example/v1';
const headers = { 'X-Orbit-Key': process.env.ORBIT_KEY, 'Content-Type': 'application/json' };

// Find a launch with room for a 4 kg CubeSat
const res = await fetch(`${BASE}/launches?status=scheduled&min_capacity_kg=4`, { headers });
const { data: launches } = await res.json();
const launch = launches[0];

// Book the slot. The Idempotency-Key makes retries safe.
const booking = await fetch(`${BASE}/bookings`, {
  method: 'POST',
  headers: { ...headers, 'Idempotency-Key': crypto.randomUUID() },
  body: JSON.stringify({
    launch_id: launch.id,
    payload: { type: 'satellite', name: 'Pixel Owl 3U', mass_kg: 4, target_orbit: 'sso' },
  }),
}).then(r => r.json());

console.log(booking.id, booking.status); // bkg_4Fh8Qp pending
```

```python Python
import os, uuid, requests

BASE = "https://api.us-east.orbit.erdman.example/v1"
headers = {"X-Orbit-Key": os.environ["ORBIT_KEY"]}

# Find a launch with room for a 4 kg CubeSat
res = requests.get(f"{BASE}/launches", params={"status": "scheduled", "min_capacity_kg": 4}, headers=headers)
launch = res.json()["data"][0]

# Book the slot. The Idempotency-Key makes retries safe.
booking = requests.post(
    f"{BASE}/bookings",
    headers={**headers, "Idempotency-Key": str(uuid.uuid4())},
    json={
        "launch_id": launch["id"],
        "payload": {"type": "satellite", "name": "Pixel Owl 3U", "mass_kg": 4, "target_orbit": "sso"},
    },
).json()

print(booking["id"], booking["status"])  # bkg_4Fh8Qp pending
```

```json Response Example
{
  "id": "bkg_4Fh8Qp",
  "launch_id": "lch_9Kd4Mw",
  "status": "pending",
  "payload": {
    "type": "satellite",
    "name": "Pixel Owl 3U",
    "mass_kg": 4,
    "target_orbit": "sso"
  },
  "insurance": "standard",
  "created_at": "2026-11-17T15:04:12Z"
}
```

# Set up the client

<!-- javascript@1-2 -->
<!-- python@1-4 -->

Every request needs your API key in the `X-Orbit-Key` header. Keep it in an environment variable, never in code.

# Find a launch

<!-- javascript@4-7 -->
<!-- python@6-8 -->

[List launches](/reference/listlaunches) with `min_capacity_kg` set to your payload’s mass. Only launches with enough free room come back.

# Book the slot

<!-- javascript@9-17 -->
<!-- python@10-17 -->

[Book a payload slot](/reference/createbooking) on that launch. `payload.type` decides which fields are required: satellites need a `target_orbit`.

# Check the result

<!-- javascript@19 -->
<!-- python@19 -->

New bookings start as `pending`. Upload the manifest next, then wait for the `booking.confirmed` webhook.