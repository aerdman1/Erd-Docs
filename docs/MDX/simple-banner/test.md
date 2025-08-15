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
/* Let Mermaid's HTML label content expand naturally */
.nodeLabel foreignObject > div,
.nodeLabel foreignObject > p,
.nodeLabel foreignObject > span {
  display: inline-flex;
  align-items: center;
  gap: 0.25em; /* space between icon and text */
}

/* Make icons consistent size and prevent overflow */
.iconify {
  width: 1em;
  height: 1em;
  vertical-align: middle;
  flex-shrink: 0;
}

</style>
`}</HTMLBlock>