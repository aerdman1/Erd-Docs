---
title: Stepper
excerpt: Click-through steps, or a vertical timeline.
deprecated: false
hidden: false
icon: fad fa-list-ol
metadata:
  robots: index
---
Break a task into steps that readers click through. The arrow keys work too, and each dot jumps straight to its step.

<SimpleStepper>
  <SimpleStep header="Find a launch">
    List launches with enough free capacity for your payload.
  </SimpleStep>

  <SimpleStep header="Book the slot">
    Create a booking. It starts as pending.
  </SimpleStep>

  <SimpleStep header="Upload the manifest">
    Attach the signed cargo manifest as a PDF.
  </SimpleStep>

  <SimpleStep header="Wait for confirmation">
    A booking.confirmed webhook tells you it’s final.
  </SimpleStep>
</SimpleStepper>

## As a timeline

Add `vertical="true"` to show every step at once:

<SimpleStepper vertical="true">
  <SimpleStep header="T−24 hours">
    Payloads are sealed in the fairing.
  </SimpleStep>

  <SimpleStep header="T−2 hours">
    Fueling starts and the range goes green.
  </SimpleStep>

  <SimpleStep header="T−0">
    Liftoff. Telemetry starts streaming.
  </SimpleStep>
</SimpleStepper>

## Use it

```mdx
<SimpleStepper>
  <SimpleStep header="Find a launch">
    List launches with room for your payload.
  </SimpleStep>

  <SimpleStep header="Book the slot">
    Create a booking.
  </SimpleStep>
</SimpleStepper>
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `vertical` | `true` | On `SimpleStepper`: show all steps as a timeline |
| `header` | Text | On `SimpleStep`: the step’s title |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * The file is named `SimpleStepperComponent`. It exports `SimpleStepper` and `SimpleStep`, and pages use those tags.
  * [Book a Launch Slot](/docs/book-a-launch-slot) uses it too.
</Accordion>
