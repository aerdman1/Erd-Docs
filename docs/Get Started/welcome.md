---
title: 欢迎来到 Orbit
excerpt: 只需一次 API 调用，即可预订可重复使用火箭的货运空间。
deprecated: false
hidden: false
icon: fad fa-rocket-launch
metadata:
  robots: index
---
Orbit 是来自 **Erdman Industries** 的发射物流 API。查找尚有空位的发射、预订有效载荷舱位、上传舱单，并一路追踪您的卫星直至入轨，全程无需离开您自己的代码。

<Callout icon="🛰️" theme="info">
  ### 这家公司完全是虚构的 {#this-whole-company-is-made-up}

  Erdman Industries 和 Orbit 并不存在。本中枢是一个用于展示 ReadMe 功能的沙盒。每个页面末尾都包含一个 **本页面构建方式** 部分，列出了该页面所使用的 ReadMe 功能。
</Callout>

## 从这里开始 {#start-here}

<Cards columns="3">
  <Card title="快速入门" href="/docs/quickstart" icon="fa-rocket" badge="5 分钟">
    列出即将进行的发射并预订测试有效载荷。
  </Card>

  <Card title="身份验证" href="/docs/authentication" icon="fa-key">
    API 密钥、OAuth 2.0 以及如何确保它们的安全。
  </Card>

  <Card title="核心概念" href="/docs/core-concepts" icon="fa-planet-ringed">
    发射、预订、有效载荷以及预订的生命周期。
  </Card>

  <Card title="预订发射舱位" href="/docs/book-a-launch-slot" icon="fa-box-taped">
    完整的预订流程，分步详解。
  </Card>

  <Card title="Webhook" href="/docs/webhooks" icon="fa-satellite-dish">
    在预订或发射发生变更的第一时间接收通知。
  </Card>

  <Card title="API 参考" href="/reference/listlaunches" icon="fa-code">
    每个端点均内置 Try It! 功能。
  </Card>
</Cards>

## 您可以构建的内容 {#what-you-can-build}

<Columns layout="auto">
  <Column>
    ### 面向卫星团队 {#for-satellite-teams}

    - 根据轨道和质量查找拼车发射舱位
    - 从发射台到部署入轨，全程追踪您的有效载荷
    - 在发射取消的第一时间获取警报
  </Column>

  <Column>
    ### 面向物流平台 {#for-logistics-platforms}

    - 在您自己的产品中转售 Orbit 运力
    - 通过 OAuth 2.0 代表您的客户进行预订
    - 使用 Account API 进行支出对账
  </Column>
</Columns>

## 下一次发射 {#next-launch}

<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" pad="LC-39X" />

## 选择运载火箭 {#pick-a-vehicle}

| 运载火箭            | LEO 有效载荷 | 典型用途       |
| :-------------- | -------: | :--------- |
| `wren`          |   900 kg | 立方星与小型拼车发射 |
| `kestrel`       | 4,000 kg | 星座批量发射     |
| `kestrel-heavy` | 6,400 kg | 空间站补给、重型货物 |

## 最新变更 {#latest-changes}

<RSS compact="true" limit="3" />

<CustomerQuotes title="发射合作伙伴评价">
  <CustomerQuote author="Dana Whitfield" role="Mission lead" company="Pixel Owl">
    我们在一个下午就完成了首颗立方星的预订。沙盒环境确保了我们的测试绝不会触及真实的火箭。
  </CustomerQuote>

  <CustomerQuote author="Ravi Menon" role="CTO" company="Hydroponics Orbital">
    Webhook 比我们自己的运营团队更早通知我们货物已完成装载。
  </CustomerQuote>
</CustomerQuotes>

<Accordion title="本页面构建方式" icon="fa-wand-magic-sparkles">
  - 带有自定义 Emoji 图标和标题的 **标注框**
  - 三列 **卡片**，带有 Font Awesome 图标、链接和徽章
  - 包含常规 Markdown 列表的 **分栏**
  - 包含左对齐和右对齐列的 Markdown **表格**
  - 三个 **自定义组件**：实时的[发射倒计时](/docs/launch-countdown)、读取本中枢 RSS 的[更新日志源](/docs/changelog-feed)以及[合作方评价](/docs/quotes)
  - 此 **折叠面板**
  - 侧边栏图标和标题下方的摘要来自页面的 frontmatter（`icon`、`excerpt`）
</Accordion>
