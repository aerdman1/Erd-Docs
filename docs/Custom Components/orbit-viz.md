---
title: Orbit Viz
excerpt: An animated diagram of the orbits Orbit flies to.
deprecated: false
hidden: false
icon: fad fa-earth-americas
metadata:
  robots: index
---
Satellites circle Earth at four altitudes. Click an orbit, or a button below the diagram, to see how high it is, how long one lap takes and what it costs.

<OrbitViz highlight="leo" />

## Use it

```mdx
<OrbitViz highlight="geo" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `highlight` | `leo`, `sso`, `meo`, `geo` | The orbit selected at first |
| `animate` | `false` | Start paused |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * It’s plain SVG with no libraries. Satellites pass behind Earth using an SVG mask.
  * **Pause** stops all motion. For readers who turn on reduced motion, it starts paused.
  * The prices and vehicle limits match the [Payload Calculator](/docs/payload-calculator).
</Accordion>
