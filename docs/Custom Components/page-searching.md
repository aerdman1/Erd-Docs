---
title: 在页面上查找
excerpt: 在此页面中搜索，并在键入时高亮显示匹配项。
deprecated: false
hidden: false
icon: fad fa-magnifying-glass
metadata:
  robots: index
---
输入即可高亮显示此页面上的匹配项。按 **Enter** 跳转到下一个匹配项，按 **Shift+Enter** 跳转到上一个匹配项。关键词标签显示每个词出现的频率。

<KeywordSearch keywords="launch, booking, manifest, webhook, telemetry" />

## 在此文本上试一试 {#try-it-on-this-text}

**发射**是指单枚运载器的单次飞行。每次发射都有发射窗口、目标轨道和空闲运力。

**预订**用于预留发射舱位。在货运清单获得批准之前，新预订将处于待处理状态。

**货运清单**是列出您货物的已签署文件。预订后请以 PDF 格式上传。

**webhook** 会在发生变更（例如确认预订或发射暂停）时通知您的服务器。

<Accordion title="遥测数据来自何处？" icon="fa-satellite-dish">
  遥测数据从 T−0 开始由运载器的飞行计算机流式传输，直至有效载荷部署完成。搜索“遥测”，此折叠面板就会自动展开。
</Accordion>

## 使用方法 {#use-it}

```mdx
<KeywordSearch keywords="launch, booking, manifest" />
```

| 属性            | 取值      | 说明                    |
| :------------ | :------ | :-------------------- |
| `keywords`    | 逗号分隔的文本 | 关键词标签。若未指定，则使用页面的关键词。 |
| `placeholder` | 文本      | 搜索框提示文本               |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 高亮显示使用浏览器的 CSS Custom Highlight API，因此页面的 HTML 绝不会发生改变。
  - 当匹配项位于已闭合的折叠面板内时，该面板会自动展开。
</Accordion>
