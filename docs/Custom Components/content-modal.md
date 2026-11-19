---
title: 模态框
excerpt: 可选详情，一键即达。
deprecated: false
hidden: false
icon: fad fa-window-restore
metadata:
  robots: index
---
将较长或可选的内容隐藏起来，直到读者需要时再显示。模态框会将键盘焦点保持在内部，可通过 **Esc** 键或点击外部区域关闭，并在手机上全屏显示。

<ContentModal label="查看有效载荷字段" title="有效载荷字段" size="md">
  | 字段             |  卫星 | 散装货物 |
  | :------------- | :-: | :--: |
  | `name`         |  ✅  |   ✅  |
  | `mass_kg`      |  ✅  |   ✅  |
  | `target_orbit` |  ✅  |      |
  | `pressurized`  |     |   ✅  |
  | `hazmat_class` |     |   ✅  |

  将 `payload.type` 设置为 `satellite` 或 `bulk_cargo`。更多信息请参阅[预订有效载荷舱位](/reference/createbooking)。
</ContentModal>

<ContentModal label="发射日规则" title="发射日规则" variant="outline" size="sm">
  1. 舱单在发射窗口开启前 24 小时锁定。
  2. 若发射取消，您的预订将免费顺延至下一个发射窗口。
  3. 遥测在 T−0 开始。
</ContentModal>

## 使用方法 {#use-it}

```mdx
<ContentModal label="See the payload fields" title="Payload fields" size="md">
  Any Markdown goes here: tables, lists, code.
</ContentModal>
```

| 属性                | 取值                           | 说明             |
| :---------------- | :--------------------------- | :------------- |
| `label`           | 文本                           | 按钮文本           |
| `title`           | 文本                           | 模态框标题          |
| `size`            | `sm`, `md`, `lg`, `xl`       | 最大宽度。默认为 `md`。 |
| `variant`         | `primary`, `outline`, `link` | 按钮样式           |
| `icon`            | 表情符号                         | 显示在标签前面        |
| `closeOnBackdrop` | `false`                      | 仅可通过关闭按钮关闭     |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 放置在标签之间的任何内容都会显示在模态框中，并且支持 Markdown。
  - 打开模态框时焦点会移入内部，关闭时则会返回到按钮。
</Accordion>
