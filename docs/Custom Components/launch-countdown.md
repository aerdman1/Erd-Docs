---
title: Launch Countdown
excerpt: A live T-minus clock for the next launch window.
deprecated: false
hidden: false
icon: fad fa-timer
metadata:
  robots: index
---
A countdown that ticks every second, shows the mission’s go/no-go status and shows the launch window in the reader’s own time zone.

<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" pad="LC-39X" />

## Holds and scrubs

Set `status` to show a hold or a scrub:

<LaunchCountdown mission="Night Heron" vehicle="wren" orbit="LEO" status="hold" />

## Use it

```mdx
<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" at="2026-12-09T03:41:00Z" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `mission` | Text | The mission name |
| `vehicle` | Text | The rocket |
| `orbit` | Text | Where it’s going |
| `pad` | Text | Optional launch pad |
| `at` | ISO 8601 time | When the window opens. Without it, the clock counts down to the next weekly window. |
| `status` | `go`, `hold`, `scrubbed` | The status light. Defaults to `go`. |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * The clock runs in the reader’s browser, so the window time is always in their time zone.
  * When the time passes, it switches to **Liftoff**.
  * For readers who turn on reduced motion, the rocket and status light stay still.
</Accordion>
