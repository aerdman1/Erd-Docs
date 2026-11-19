---
title: Orbit 可视化
excerpt: Orbit 飞往各轨道的动态示意图。
deprecated: false
hidden: false
icon: fad fa-earth-americas
metadata:
  robots: index
---
卫星在四个不同高度环绕地球运行。点击某条轨道或图表下方的按钮，即可查看其高度、绕行一圈所需时间以及费用。

<OrbitViz highlight="leo" />

## 使用方法 {#use-it}

```mdx
<OrbitViz highlight="geo" />
```

| 属性          | 取值                         | 作用      |
| :---------- | :------------------------- | :------ |
| `highlight` | `leo`, `sso`, `meo`, `geo` | 初始选中的轨道 |
| `animate`   | `false`                    | 以暂停状态启动 |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 这是不依赖任何库的纯 SVG。卫星使用 SVG 蒙版从地球后方穿过。
  - **暂停**会停止所有运动。对于开启了减少动态效果的读者，它在启动时处于暂停状态。
  - 价格和运载工具限制与[有效载荷计算器](/docs/payload-calculator)一致。
</Accordion>
