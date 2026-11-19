---
title: 客户感言
excerpt: 轮播展示的客户感言。
deprecated: false
hidden: false
icon: fad fa-quote-left
metadata:
  robots: index
---
引述内容会自动轮播，并在读者悬停或按 Tab 键聚焦时暂停。

<CustomerQuotes title="发射合作伙伴评价">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    我们在一个下午就预订了首颗 CubeSat。沙箱环境意味着我们的测试从未接触过真正的火箭。
  </CustomerQuote>

  <CustomerQuote author="Ravi Menon" role="CTO" company="Hydroponics Orbital">
    Webhook 比我们自己的运营团队更早通知我们货物已装载完毕。
  </CustomerQuote>

  <CustomerQuote author="Lucía Ortega" role="Founder" company="Long Reach Labs">
    在发射周遭遇网络中断期间，幂等键避免了我们进行重复预订。
  </CustomerQuote>
</CustomerQuotes>

这些人物和公司纯属虚构。

## 使用方法 {#use-it}

```mdx
<CustomerQuotes title="What launch partners say">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    We booked our first CubeSat in an afternoon.
  </CustomerQuote>
</CustomerQuotes>
```

| 属性                          | 取值      | 作用                           |
| :-------------------------- | :------ | :--------------------------- |
| `title`                     | 文本      | 用于 `CustomerQuotes`：标题       |
| `autoplay`                  | `false` | 关闭自动轮播                       |
| `interval`                  | 秒数      | 每条引述的停留时间。默认为 7。             |
| `author`, `role`, `company` | 文本      | 用于 `CustomerQuote`           |
| `avatar`                    | 图片 URL  | 用于 `CustomerQuote`：替换姓名首字母缩写 |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 对于开启了减少动态效果的读者，它会停止轮播。
</Accordion>
