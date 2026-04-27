---
title: RSS Release Notes
deprecated: false
hidden: true
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<ChangelogRssFeed rssUrl="/changelog.rss" maxItems={1250} cacheMinutes={0} />

<HTMLBlock>{`
<style>
section.content-toc.grid-25 {
    display: none;
  }

.rm-Guides .content-body {
    -ms-flex-negative: 1;
    flex-shrink: 1;
    max-width: 100%;
    padding-top: 30px;
    width: 100%;
}
</style>
`}</HTMLBlock>

<br />

<Cards>
  <Card title="Full code quickstart" href="/docs/content-modal" icon="fa-code">
    Build a complete verification flow using the MiVIP APIs.
  </Card>

  <Card title="Low code quickstart" href="doc:low-code" icon="fa-puzzle-piece">
    Create a verification journey using the MiVIP console configuration and minimal API calls.
  </Card>

  <Card title="No code quickstart" href="doc:no-code" icon="fa-mouse-pointer">
    Set up your first verification journey using the MiVIP console without writing any code.
  </Card>
</Cards>