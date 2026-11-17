---
title: Payload Calculator
excerpt: Price a payload and get the exact request to book it.
deprecated: false
hidden: false
icon: fad fa-calculator
metadata:
  robots: index
---
Pick a payload, a mass and an orbit. The calculator shows which vehicles can lift it and what it costs, and writes the request for [Book a payload slot](/reference/createbooking), ready to copy.

<PayloadCalculator />

Try 3,000 kg to GEO to see the `422` error the API would send back.

## Use it

```mdx
<PayloadCalculator type="satellite" mass="12" orbit="sso" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `type` | `satellite`, `bulk_cargo` | The starting payload type |
| `mass` | Kilograms | The starting mass. Defaults to 4. |
| `orbit` | `leo`, `sso`, `meo`, `geo` | The starting orbit |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * Vehicle capacities and field values match the Orbit API definition, so the JSON it writes is a valid request.
  * The mass slider is logarithmic, so 4 kg CubeSats and 4,000 kg cargo both fit on one slider.
  * **Copy** works inside ReadMe’s editor preview too.
</Accordion>
