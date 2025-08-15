---
title: Mermaid
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
iconify

```mermaid
flowchart LR
  A[<span class="iconify" data-icon="mingcute:rocket-line"></span> Launch]
  A --> B[<span class="iconify" data-icon="tabler:circle-check"></span> Done]

```

<HTMLBlock>{`
<style>
/* Keep icon inline and text-aligned */
.iconify {
  width: 1em;     /* important: size like a character */
  height: 1em;
  vertical-align: -0.125em;
  line-height: 1;
}

/* Tighten label contents */
svg .label foreignObject > div { 
  display: inline-flex;
  align-items: center;

}
svg .label p { margin: 0; display: inline-flex; align-items: center; gap: 0.25em; }

</style>
`}</HTMLBlock>