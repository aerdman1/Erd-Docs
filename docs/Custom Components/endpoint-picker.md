---
title: Endpoint Picker
excerpt: Browse every endpoint from one dropdown.
deprecated: false
hidden: false
icon: fad fa-list-tree
metadata:
  robots: index
---
Pick any endpoint in the hub’s API definitions to see its parameters and a sample request. It finds the definitions on its own, so new endpoints show up here without editing the page.

<EndpointPicker />

## Use it

```mdx
<EndpointPicker />
```

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * It reads the list of API definitions from the hub’s `/openapi` page, then loads the one you pick.
  * It follows the hub’s light or dark mode.
</Accordion>
