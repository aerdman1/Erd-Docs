---
title: Verify webhook signatures
description: Check that a webhook really came from Orbit before you act on it.
hidden: false
recipe:
  color: '#7B3FF2'
  icon: 🔏
---
```javascript Node.js
import express from 'express';
import crypto from 'node:crypto';

const app = express();

// Keep the raw bytes: the signature covers the body exactly as sent
app.post('/hooks/orbit', express.raw({ type: 'application/json' }), (req, res) => {
  const header = req.get('Orbit-Signature'); // t=1763391852,v1=5f2b…
  const { t, v1 } = Object.fromEntries(header.split(',').map(p => p.split('=')));

  // Reject anything older than five minutes
  if (Math.abs(Date.now() / 1000 - Number(t)) > 300) return res.sendStatus(400);

  const expected = crypto
    .createHmac('sha256', process.env.ORBIT_WEBHOOK_SECRET)
    .update(`${t}.${req.body}`)
    .digest('hex');
  if (!crypto.timingSafeEqual(Buffer.from(expected), Buffer.from(v1))) return res.sendStatus(400);

  const event = JSON.parse(req.body);
  console.log(event.type, event.data.id); // booking.confirmed bkg_4Fh8Qp
  res.sendStatus(204);
});

app.listen(3000);
```

# Read the raw body

<!-- javascript@6-7 -->

The signature covers the request body byte for byte, so take it raw. Parsing JSON and serializing it again changes the bytes.

# Split the header

<!-- javascript@8-9 -->

`Orbit-Signature` holds a Unix timestamp `t` and the signature `v1`.

# Check the timestamp

<!-- javascript@11-12 -->

Refuse events more than five minutes old, so an old request can’t be replayed.

# Compare signatures

<!-- javascript@14-18 -->

Sign `t.body` with your webhook secret and compare in constant time.

# Handle the event

<!-- javascript@20-22 -->

Reply with any `2xx` within ten seconds. Otherwise Orbit retries with backoff, up to five times.