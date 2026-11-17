---
title: Welcome to Orbit
excerpt: Book cargo space on reusable rockets with one API call.
deprecated: false
hidden: false
icon: fad fa-rocket-launch
metadata:
  robots: index
---
Orbit is the launch-logistics API from **Erdman Industries**. Find a launch with room to spare, book a payload slot, upload your manifest and follow your satellite all the way to orbit, without leaving your own code.

<Callout icon="🛰️" theme="info">
  ### This whole company is made up

  Erdman Industries and Orbit don’t exist. This hub is a sandbox that shows off what ReadMe can do. Every page ends with a **How this page is built** section that lists the ReadMe features on it.
</Callout>

## Start here

<Cards columns="3">
  <Card title="Quickstart" href="/docs/quickstart" icon="fa-rocket" badge="5 min">
    List upcoming launches and book a test payload.
  </Card>

  <Card title="Authentication" href="/docs/authentication" icon="fa-key">
    API keys, OAuth 2.0 and how to keep them safe.
  </Card>

  <Card title="Core concepts" href="/docs/core-concepts" icon="fa-planet-ringed">
    Launches, bookings, payloads and the life of a booking.
  </Card>

  <Card title="Book a launch slot" href="/docs/book-a-launch-slot" icon="fa-box-taped">
    The full booking flow, step by step.
  </Card>

  <Card title="Webhooks" href="/docs/webhooks" icon="fa-satellite-dish">
    Hear the moment a booking or a launch changes.
  </Card>

  <Card title="API Reference" href="/reference/listlaunches" icon="fa-code">
    Every endpoint, with Try It! built in.
  </Card>
</Cards>

## What you can build

<Columns layout="auto">
  <Column>
    ### For satellite teams

    * Find rideshare slots by orbit and mass
    * Follow your payload from the pad to deployment
    * Get an alert the moment a launch scrubs
  </Column>

  <Column>
    ### For logistics platforms

    * Resell Orbit capacity inside your own product
    * Book on behalf of your customers with OAuth 2.0
    * Reconcile spend with the Account API
  </Column>
</Columns>

## Next launch

<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" pad="LC-39X" />

## Pick a vehicle

| Vehicle         | Payload to LEO | Typical use                    |
| :-------------- | -------------: | :----------------------------- |
| `wren`          |         900 kg | CubeSats and small rideshares  |
| `kestrel`       |       4,000 kg | Constellation batches          |
| `kestrel-heavy` |       6,400 kg | Station resupply, heavy cargo  |

## Latest changes

<RSS compact="true" limit="3" />

<CustomerQuotes title="What launch partners say">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    We booked our first CubeSat in an afternoon. The sandbox meant our tests never touched a real rocket.
  </CustomerQuote>

  <CustomerQuote author="Ravi Menon" role="CTO" company="Hydroponics Orbital">
    Webhooks told us our cargo was loaded before our own ops team did.
  </CustomerQuote>
</CustomerQuotes>

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * **Callout** with a custom emoji icon and a title
  * **Cards** in three columns, with Font Awesome icons, links and a badge
  * **Columns** holding regular Markdown lists
  * A Markdown **table** with left- and right-aligned columns
  * Three **custom components**: a live [launch countdown](/docs/launch-countdown), a [changelog feed](/docs/changelog-feed) that reads the hub’s RSS, and [testimonials](/docs/quotes)
  * This **Accordion**
  * The sidebar icon and the summary under the title come from the page’s frontmatter (`icon`, `excerpt`)
</Accordion>
