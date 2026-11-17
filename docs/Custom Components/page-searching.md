---
title: Find on Page
excerpt: Search this page and highlight matches as you type.
deprecated: false
hidden: false
icon: fad fa-magnifying-glass
metadata:
  robots: index
---
Type to highlight matches on this page. **Enter** jumps to the next match and **Shift+Enter** to the previous one. The keyword chips show how often each term appears.

<KeywordSearch keywords="launch, booking, manifest, webhook, telemetry" />

## Try it on this text

A **launch** is one flight of one vehicle. Each launch has a window, a target orbit and free capacity.

A **booking** reserves space on a launch. New bookings are pending until the manifest is approved.

The **manifest** is the signed document that lists your cargo. Upload it as a PDF after booking.

A **webhook** tells your server when something changes, such as a confirmed booking or a launch hold.

<Accordion title="Where does telemetry come from?" icon="fa-satellite-dish">
  Telemetry streams from the vehicle’s flight computer from T−0 until the payload is deployed. Search for “telemetry” and this accordion opens itself.
</Accordion>

## Use it

```mdx
<KeywordSearch keywords="launch, booking, manifest" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `keywords` | Comma-separated text | The keyword chips. Without it, the page’s keywords are used. |
| `placeholder` | Text | The search box hint |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * Highlights use the browser’s CSS Custom Highlight API, so the page’s HTML never changes.
  * When a match is inside a closed accordion, it opens.
</Accordion>
