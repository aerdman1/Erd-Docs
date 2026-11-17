---
title: Book a Launch Slot
excerpt: The full booking flow, from finding a launch to a confirmed slot.
deprecated: false
hidden: false
icon: fad fa-box-taped
metadata:
  robots: index
---
Booking takes four steps. Click through them, then read the details below.

<SimpleStepper>
  <SimpleStep header="1. Find a launch">
    List launches with enough free capacity for your payload.
  </SimpleStep>

  <SimpleStep header="2. Book the slot">
    Create a booking. It starts as pending.
  </SimpleStep>

  <SimpleStep header="3. Upload the manifest">
    Attach the signed cargo manifest as a PDF.
  </SimpleStep>

  <SimpleStep header="4. Wait for confirmation">
    A booking.confirmed webhook tells you it’s final.
  </SimpleStep>
</SimpleStepper>

## Before you start

* [x] You have an API key ([Authentication](/docs/authentication))
* [x] You know your payload’s mass and target orbit
* [ ] Your manifest is signed and saved as a PDF
* [ ] You have a webhook endpoint ready ([Webhooks](/docs/webhooks))

## 1. Find a launch

Call [List launches](/reference/listlaunches) with `min_capacity_kg` set to your payload’s mass. Filter by `vehicle` if your payload needs a specific one.

## 2. Book the slot

Call [Book a payload slot](/reference/createbooking). The `payload.type` field decides which other fields are required:

<Tabs>
  <Tab title="Satellite" icon="fa-satellite">
    ```json
    {
      "launch_id": "lch_9Kd4Mw",
      "payload": {
        "type": "satellite",
        "name": "Pixel Owl 3U",
        "mass_kg": 4,
        "target_orbit": "sso",
        "deploy_altitude_km": 525
      },
      "insurance": "standard"
    }
    ```
  </Tab>

  <Tab title="Bulk cargo" icon="fa-boxes-stacked">
    ```json
    {
      "launch_id": "lch_7Hq2Zr",
      "payload": {
        "type": "bulk_cargo",
        "name": "Hydroponics resupply",
        "mass_kg": 820,
        "pressurized": true,
        "hazmat_class": "none"
      },
      "insurance": "premium"
    }
    ```
  </Tab>
</Tabs>

<Callout icon="📘" theme="info">
  ### Retries are safe

  Send a fresh UUID in the `Idempotency-Key` header with each new booking. If the network drops and you retry with the same key, Orbit returns the original booking instead of booking twice.
</Callout>

## 3. Upload the manifest

Send the signed PDF to [Upload a cargo manifest](/reference/uploadmanifest) as `multipart/form-data`:

```javascript upload-manifest.js
import fs from 'node:fs';

const form = new FormData();
form.append('file', new Blob([fs.readFileSync('manifest.pdf')]), 'manifest.pdf');
form.append('signed_by', 'Dana Whitfield');

await fetch(`https://api.us-east.orbit.erdman.example/v1/bookings/${bookingId}/manifest`, {
  method: 'POST',
  headers: { 'X-Orbit-Key': process.env.ORBIT_KEY },
  body: form,
});
```

## 4. Wait for confirmation

Orbit reviews manifests within one business day. When it approves yours, the booking moves to `confirmed` and you get a [booking.confirmed](/reference/bookingconfirmed) webhook.

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * A **custom component**: `SimpleStepper`, written in MDX and stored with the project
  * A **checklist** using Markdown task-list syntax
  * **Tabs** holding JSON examples for each `oneOf` payload type
  * A **code block with a file name** as its title
  * An **info** Callout
</Accordion>
