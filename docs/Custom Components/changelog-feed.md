---
title: Changelog Feed
excerpt: The latest changelog posts on any page.
deprecated: false
hidden: false
icon: fad fa-rss
metadata:
  robots: index
---
Pull changelog posts into any page. It reads the hub’s own RSS feed, so new posts appear here without editing this page. Filter by type or search.

<RSS limit="10" />

## Compact

A short list fits on a landing or welcome page:

<RSS compact="true" limit="3" title="Latest changes" />

## Use it

```mdx
<RSS limit="10" />

<RSS compact="true" limit="3" title="Latest changes" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `limit` | Number | How many posts to show. Defaults to 20. |
| `compact` | `true` | A short list instead of the timeline |
| `title` | Text | A heading for the compact list |
| `filters` | `false` | Hide the type filters and search |
| `type` | `added`, `improved`, `fixed`, `deprecated`, `removed` | Start filtered to one type |
| `url` | Path | Another feed. Defaults to `/changelog.rss`. |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * The feed is cached for five minutes in the reader’s browser.
  * Type labels come from each post’s type in the changelog.
</Accordion>
