---
title: Modal
excerpt: Optional detail, one click away.
deprecated: false
hidden: false
icon: fad fa-window-restore
metadata:
  robots: index
---
Keep long or optional content out of the way until a reader asks for it. The modal keeps keyboard focus inside, closes with **Esc** or a click outside, and fills the screen on phones.

<ContentModal label="See the payload fields" title="Payload fields" size="md">
  | Field          | Satellite | Bulk cargo |
  | :------------- | :-------: | :--------: |
  | `name`         | ✅        | ✅         |
  | `mass_kg`      | ✅        | ✅         |
  | `target_orbit` | ✅        |            |
  | `pressurized`  |           | ✅         |
  | `hazmat_class` |           | ✅         |

  Set `payload.type` to `satellite` or `bulk_cargo`. Read more in [Book a payload slot](/reference/createbooking).
</ContentModal>

<ContentModal label="Launch day rules" title="Launch day rules" variant="outline" size="sm">
  1. Manifests lock 24 hours before the window opens.
  2. A scrubbed launch rolls your booking to the next window for free.
  3. Telemetry starts at T−0.
</ContentModal>

## Use it

```mdx
<ContentModal label="See the payload fields" title="Payload fields" size="md">
  Any Markdown goes here: tables, lists, code.
</ContentModal>
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `label` | Text | The button text |
| `title` | Text | The modal’s heading |
| `size` | `sm`, `md`, `lg`, `xl` | Maximum width. Defaults to `md`. |
| `variant` | `primary`, `outline`, `link` | The button style |
| `icon` | Emoji | Shown before the label |
| `closeOnBackdrop` | `false` | Only the close button closes it |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * Whatever you put between the tags shows in the modal, and Markdown works there.
  * Focus moves into the modal when it opens and back to the button when it closes.
</Accordion>
