---
title: Custom Components
excerpt: React components written in MDX, used on any page like a built-in block.
deprecated: false
hidden: false
icon: fad fa-puzzle-piece
metadata:
  robots: index
---
Built-in blocks cover most pages. When you need something they can’t do, write a **custom component**: a React component in an MDX file, saved with the project under **Components** in the dashboard. Any page can then use it with a tag, the same way it uses a Callout or Tabs.

Every component in this section is one of those files. Each page shows it live, then how to use it.

<Cards columns="3">
  <Card title="Countdown" href="/docs/launch-countdown" icon="fa-timer" iconColor="#7B3FF2" badge="New">
    A live T-minus clock in the reader’s time zone.
  </Card>

  <Card title="Payload Calculator" href="/docs/payload-calculator" icon="fa-calculator" iconColor="#2F7BF5" badge="New">
    Price a payload and get the exact API request.
  </Card>

  <Card title="Orbit Viz" href="/docs/orbit-viz" icon="fa-earth-americas" iconColor="#19C3F5" badge="New">
    An animated orbit diagram you can explore.
  </Card>

  <Card title="Terminal" href="/docs/terminal" icon="fa-terminal" iconColor="#12B76A" badge="New">
    A CLI session that types itself out.
  </Card>

  <Card title="API Key Card" href="/docs/api-key-card" icon="fa-key" iconColor="#F79009" badge="New">
    Shows signed-in readers their own key.
  </Card>

  <Card title="Changelog Feed" href="/docs/changelog-feed" icon="fa-rss" iconColor="#F04438" badge="New">
    The latest changelog posts on any page.
  </Card>

  <Card title="Stepper" href="/docs/simple-stepper" icon="fa-list-ol">
    Click-through steps, or a vertical timeline.
  </Card>

  <Card title="Banners" href="/docs/simple-banner" icon="fa-flag">
    Inline or site-wide announcements.
  </Card>

  <Card title="Modal" href="/docs/content-modal" icon="fa-window-restore">
    Optional detail, one click away.
  </Card>

  <Card title="Endpoint Chips" href="/docs/endpoint-embedding-lite" icon="fa-link">
    Endpoint previews that read the API definition.
  </Card>

  <Card title="Endpoint Picker" href="/docs/endpoint-picker" icon="fa-list-tree">
    Browse every endpoint from one dropdown.
  </Card>

  <Card title="Find on Page" href="/docs/page-searching" icon="fa-magnifying-glass">
    Search and highlight as you type.
  </Card>

  <Card title="Testimonials" href="/docs/quotes" icon="fa-quote-left">
    A rotating carousel of quotes.
  </Card>

  <Card title="SDK Explorer" href="/docs/sdk-explorer" icon="fa-cube">
    Browse a package’s API from its types.
  </Card>
</Cards>

## How they’re built

<Columns layout="auto">
  <Column>
    **One file each**

    Each component is an MDX file that exports a React component with the same name as the file.
  </Column>

  <Column>
    **Plain string props**

    Pages pass props as strings, like `vertical="true"`, so they’re easy to write in the editor.
  </Column>

  <Column>
    **Themed by the hub**

    Colors come from the hub’s own theme variables, so every component matches light and dark mode.
  </Column>
</Columns>

<Callout icon="📘" theme="info">
  Custom components run in the reader’s browser with React. They can read the signed-in reader’s login data, fetch from the hub, and use any browser API. See [API Key Card](/docs/api-key-card) for an example.
</Callout>
