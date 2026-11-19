---
title: Endpoint 选择器
excerpt: 在一个下拉菜单中浏览所有 endpoint。
deprecated: false
hidden: false
icon: fad fa-list-tree
metadata:
  robots: index
---
在 hub 的 API 定义中挑选任意端点，或按路径、方法或摘要进行搜索。你可以获取指向其参考页面的链接、可直接粘贴的 Markdown 链接，只需点击一下即可查看完整定义。它会自动查找定义，因此无需编辑页面，新端点就会显示在此处。

<EndpointPicker />

## 使用它 {#use-it}

```mdx
<EndpointPicker />
```

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 它会从 hub 的 `/openapi` 页面读取 API 定义列表，然后加载你所选的内容。
  - 它会遵循 hub 的浅色或深色模式。
</Accordion>
