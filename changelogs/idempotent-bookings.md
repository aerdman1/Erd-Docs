---
title: Retry bookings safely with Idempotency-Key
type: improved
hidden: false
published_at: '2026-11-03T15:00:00.000Z'
author: Andrew Erdman
---
[Book a payload slot](/reference/createbooking) now accepts an `Idempotency-Key` header. If a request times out and you retry it with the same key, you get the original booking back instead of a second one.

> 👍 No code change needed
>
> Requests without the header work exactly as before.
