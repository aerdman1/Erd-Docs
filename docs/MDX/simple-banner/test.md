---
title: Mermaid
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
```mermaid
flowchart LR
  A --- B[mingcute:rocket-line Rocket]
  B --> C[tabler:circle-check Done]
  B --> D[mdi:close-thick Cancel]

flowchart TD
  Start[heroicons-outline:play Start] --> Build[bi:braces Code]
  Build --> Test[heroicons-outline:beaker Testing]
  Test --> Ship[logos:vercel Deploy]

```