---
title: Quickstart
excerpt: Make your first Orbit request in about five minutes.
deprecated: false
hidden: false
icon: fad fa-rocket
metadata:
  robots: index
---
By the end of this page you’ll have listed upcoming launches and booked a test payload.

## 1. Get an API key

Log in to Orbit, open **Account → API keys** and create a key. Test keys start with `ok_test_` and never charge you.

<Callout icon="🔑" theme="warn">
  Keep secret keys on your server. Anyone who has your key can book launches on your account.
</Callout>

When you’re logged in to this hub, the [API Reference](/reference/listlaunches) fills your key in for you, so **Try It!** works straight away.

## 2. Find a launch with room

Ask for launches that still have at least 4 kg of free capacity:

```shell cURL
curl "https://api.us-east.orbit.erdman.example/v1/launches?min_capacity_kg=4" \
  -H "X-Orbit-Key: $ORBIT_KEY"
```
```javascript Node.js
const res = await fetch('https://api.us-east.orbit.erdman.example/v1/launches?min_capacity_kg=4', {
  headers: { 'X-Orbit-Key': process.env.ORBIT_KEY },
});
const { data } = await res.json();

for (const launch of data) {
  console.log(`${launch.name}: ${launch.capacity.available_kg} kg free`);
}
```
```python Python
import os
import requests

res = requests.get(
    "https://api.us-east.orbit.erdman.example/v1/launches",
    params={"min_capacity_kg": 4},
    headers={"X-Orbit-Key": os.environ["ORBIT_KEY"]},
)
for launch in res.json()["data"]:
    print(f'{launch["name"]}: {launch["capacity"]["available_kg"]} kg free')
```

You get back a page of launches, soonest first:

```json
{
  "data": [
    {
      "id": "lch_9Kd4Mw",
      "name": "Polaris Run",
      "vehicle": "wren",
      "status": "go",
      "capacity": { "total_kg": 900, "available_kg": 120 },
      "target_orbit": "sso"
    }
  ],
  "has_more": true,
  "next_cursor": "Y3Vyc29yOjI="
}
```

## 3. Book a test payload

Book a 4 kg CubeSat on the launch you found. The `Idempotency-Key` header makes the request safe to retry.

```shell cURL
curl -X POST "https://api.us-east.orbit.erdman.example/v1/bookings" \
  -H "X-Orbit-Key: $ORBIT_KEY" \
  -H "Content-Type: application/json" \
  -H "Idempotency-Key: $(uuidgen)" \
  -d '{
    "launch_id": "lch_9Kd4Mw",
    "payload": { "type": "satellite", "name": "Pixel Owl 3U", "mass_kg": 4, "target_orbit": "sso" }
  }'
```
```javascript Node.js
import { randomUUID } from 'node:crypto';

const res = await fetch('https://api.us-east.orbit.erdman.example/v1/bookings', {
  method: 'POST',
  headers: {
    'X-Orbit-Key': process.env.ORBIT_KEY,
    'Content-Type': 'application/json',
    'Idempotency-Key': randomUUID(),
  },
  body: JSON.stringify({
    launch_id: 'lch_9Kd4Mw',
    payload: { type: 'satellite', name: 'Pixel Owl 3U', mass_kg: 4, target_orbit: 'sso' },
  }),
});
console.log(await res.json()); // status: "pending"
```

The booking comes back as `pending`. It moves to `confirmed` once Orbit reviews your cargo manifest.

<Callout icon="🎉" theme="okay">
  ### You booked your first launch

  Next, [upload a manifest](/docs/book-a-launch-slot) and [set up webhooks](/docs/webhooks) so you hear when the booking is confirmed.
</Callout>

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * Numbered **headings**, which also build the table of contents on the right
  * **Code tabs**: back-to-back code blocks, each with a language and a tab name, turn into one tabbed block
  * A plain **code block** with JSON syntax highlighting
  * **Callouts** in the warning and success themes
  * Links to other guides and to the **API Reference**
</Accordion>
