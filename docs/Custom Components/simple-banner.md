---
title: Banners
excerpt: Announcements on a page, or across the top of the site.
deprecated: false
hidden: false
icon: fad fa-flag
metadata:
  robots: index
---
Five styles for news, notices and warnings. Add a link, and let readers dismiss a banner for the rest of their visit.

<SimpleBanner variant="launch" message="Bulk cargo bookings are live." link="/changelog/bulk-cargo-bookings" linkText="See what’s new" />

<SimpleBanner variant="info" message="Orbit API 1.4 is out." />

<SimpleBanner variant="success" message="All systems are operational." link="/page/status" linkText="Mission Control" />

<SimpleBanner variant="warn" message="The launch weather endpoint stops working on March 1, 2027." link="/reference/getlaunchweather" linkText="Migrate" dismissible="true" />

<SimpleBanner variant="error" message="Legacy v0 booking endpoints are gone." link="/changelog/v0-bookings-removed" linkText="Details" />

## In the site header

With `placement="header"`, the banner runs across the top of the site while this page is open. Look up: it’s there now.

<SimpleBanner placement="header" variant="launch" message="This banner lives in the site header while you’re on this page." dismissible="true" />

## Use it

```mdx
<SimpleBanner variant="warn" message="Maintenance on Saturday." link="/page/status" linkText="Status" dismissible="true" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `message` | Text | What the banner says |
| `variant` | `info`, `success`, `warn`, `error`, `launch` | The style |
| `icon` | Emoji | Replaces the variant’s icon |
| `link`, `linkText` | URL, text | An optional link at the end |
| `placement` | `inline`, `header` | Where it shows. `header` puts it across the top of the site. |
| `dismissible` | `true` | Adds a close button. It stays closed for the rest of the visit. |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * A header banner is added when the page opens and removed when the reader leaves it.
  * Older pages that pass `isHeader`, `bannerColor` and `bannerTextColor` still work.
</Accordion>
