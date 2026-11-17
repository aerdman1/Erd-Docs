---
title: Telemetry timestamps no longer drift
type: fixed
hidden: false
published_at: '2026-10-20T15:00:00.000Z'
author: Andrew Erdman
---
Samples from [Get payload telemetry](/reference/gettelemetry) at the `1s` interval could drift by up to a second during long coast phases. Timestamps now come from the vehicle’s flight computer clock and line up exactly.
