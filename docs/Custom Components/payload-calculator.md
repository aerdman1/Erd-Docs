---
title: 有效载荷计算器
excerpt: 计算有效载荷的价格，并获取用于预订的准确请求。
deprecated: false
hidden: false
icon: fad fa-calculator
metadata:
  robots: index
---
选择有效载荷、质量和轨道。计算器会显示哪些运载工具能够承载它及其费用，并生成[预订有效载荷舱位](/reference/createbooking)请求，可随时复制。

<PayloadCalculator />

尝试选择 3,000 kg 到 GEO，以查看 API 会返回的 `422` 错误。

## 使用方法 {#use-it}

```mdx
<PayloadCalculator type="satellite" mass="12" orbit="sso" />
```

| 属性      | 取值                         | 作用          |
| :------ | :------------------------- | :---------- |
| `type`  | `satellite`, `bulk_cargo`  | 初始有效载荷类型    |
| `mass`  | 千克                         | 初始质量。默认为 4。 |
| `orbit` | `leo`, `sso`, `meo`, `geo` | 初始轨道        |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 运载工具运力及字段值与 Orbit API 定义相符，因此它生成的 JSON 是一个有效请求。
  - 质量滑块采用对数刻度，因此 4 kg 的立方体卫星和 4,000 kg 的货物都可以容纳在同一个滑块上。
  - **复制**在 ReadMe 的编辑器预览中也同样有效。
</Accordion>
