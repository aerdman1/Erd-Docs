---
title: Endpoint Chips
excerpt: Endpoint previews that read the API definition.
deprecated: false
hidden: false
icon: fad fa-link
metadata:
  robots: index
---
Mention an endpoint in a sentence, and readers can hover over it or tab to it for a preview. Give it an `operationId` and it reads the method, title and description from the API definition, so it never goes stale.

Find a launch with <EndpointEmbedLite operationId="listLaunches" />, book it with <EndpointEmbedLite operationId="createBooking" />, then wait for <EndpointEmbedLite operationId="bookingConfirmed" />.

## As a card

<EndpointEmbedLite operationId="uploadManifest" displayMode="card" />

<EndpointEmbedLite operationId="getLaunchWeather" displayMode="card" />

Deprecated endpoints are flagged automatically.

## Use it

```mdx
Book it with <EndpointEmbedLite operationId="createBooking" />.

<EndpointEmbedLite operationId="uploadManifest" displayMode="card" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `operationId` | Text | The endpoint or webhook to show |
| `displayMode` | `popup`, `chip`, `card` | A chip with a preview, a plain chip, or a full card |
| `spec` | File name | Which API definition to read. Defaults to `orbit.yaml`. |
| `linkText` | Text | Replaces the chip’s label |
| `method`, `endpoint`, `title`, `description` | Text | Set these to skip the API definition |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * It reads the API definition from the hub at `/openapi/orbit.yaml`, once per page.
  * Each chip links to the endpoint’s page in the API Reference.
</Accordion>
