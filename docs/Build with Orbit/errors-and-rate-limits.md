---
title: Errors & Rate Limits
excerpt: What Orbit’s errors mean, and how to stay under the rate limit.
deprecated: false
hidden: false
icon: fad fa-triangle-exclamation
metadata:
  robots: index
---
Orbit uses standard HTTP status codes. Every error body is an [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) *problem details* object, so one handler covers them all:

```json
{
  "type": "https://erdman.readme.io/docs/errors-and-rate-limits#launch-full",
  "title": "Launch is full",
  "status": 409,
  "detail": "Polaris Run has 120 kg free and this payload is 820 kg."
}
```

## Status codes

| Code  | Meaning                                    | Retry?                       |
| :---: | :----------------------------------------- | :--------------------------- |
| `400` | The request is malformed                   | No, fix the request          |
| `401` | The API key is missing or invalid          | No                           |
| `404` | Nothing exists with that ID                | No                           |
| `409` | The launch is full                         | Yes, on a different launch   |
| `422` | The payload can’t reach its target orbit   | Yes, on a bigger vehicle     |
| `429` | Rate limited                               | Yes, after `Retry-After`     |
| `5xx` | Something broke on our side                | Yes, with backoff            |

## Common errors

### Unauthorized

<Callout icon="❗️" theme="error">
  `401` means the `X-Orbit-Key` header is missing, or the key was rolled. Live keys don’t work against test data, and test keys don’t work against live data.
</Callout>

### Launch full

<Callout icon="⚠️" theme="warn">
  `409` means someone booked the last kilograms before you. Call [List launches](/reference/listlaunches) with `min_capacity_kg` to find another launch.
</Callout>

### Delta-v exceeded

<Callout icon="🚀" theme="default">
  `422` means the vehicle can’t lift that mass to that orbit[^1]. A `wren` reaches GEO with about 150 kg, so move heavy payloads to a `kestrel-heavy`.
</Callout>

## Rate limits

Each key gets 120 requests a minute. Every response tells you where you stand:

| Header                  | Example | Meaning                                      |
| :---------------------- | :------ | :------------------------------------------- |
| `X-RateLimit-Remaining` | `118`   | Requests left in this one-minute window       |
| `Retry-After`           | `12`    | Seconds to wait (only on `429` responses)     |

<Callout icon="📘" theme="info">
  Need more? The **Fleet** plan raises the limit to 1,200 requests a minute. Check your current usage with [Get account usage](/reference/getusage).
</Callout>

<Callout icon="👍" theme="okay">
  Webhooks don’t count toward your rate limit. Use them instead of polling launch status.
</Callout>

[^1]: The rocket equation is not negotiable, even for a made-up company.

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * **Callouts** in every theme: error, warning, default, info and success
  * Level-3 **headings** that the API Reference links to by anchor (`#launch-full`)
  * A **table** with a centered column
  * A **footnote**
  * Italic, bold and inline code in running text
</Accordion>
