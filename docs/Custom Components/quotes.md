---
title: Testimonials
excerpt: A rotating carousel of customer quotes.
deprecated: false
hidden: false
icon: fad fa-quote-left
metadata:
  robots: index
---
Quotes rotate on their own and pause while the reader hovers or tabs into them.

<CustomerQuotes title="What launch partners say">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    We booked our first CubeSat in an afternoon. The sandbox meant our tests never touched a real rocket.
  </CustomerQuote>

  <CustomerQuote author="Ravi Menon" role="CTO" company="Hydroponics Orbital">
    Webhooks told us our cargo was loaded before our own ops team did.
  </CustomerQuote>

  <CustomerQuote author="Lucía Ortega" role="Founder" company="Long Reach Labs">
    Idempotency keys saved us from double-booking during a network outage at launch week.
  </CustomerQuote>
</CustomerQuotes>

These people and companies are made up.

## Use it

```mdx
<CustomerQuotes title="What launch partners say">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    We booked our first CubeSat in an afternoon.
  </CustomerQuote>
</CustomerQuotes>
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `title` | Text | On `CustomerQuotes`: the heading |
| `autoplay` | `false` | Turn off auto-rotation |
| `interval` | Seconds | Time per quote. Defaults to 7. |
| `author`, `role`, `company` | Text | On `CustomerQuote` |
| `avatar` | Image URL | On `CustomerQuote`: replaces the initials |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * It stops rotating for readers who turn on reduced motion.
</Accordion>
