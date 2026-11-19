---
title: 横幅
excerpt: 页面内或网站顶部的公告。
deprecated: false
hidden: false
icon: fad fa-flag
metadata:
  robots: index
---
适用于新闻、通知和警告的五种样式。添加链接，并允许读者在本次访问的剩余时间内关闭横幅。

<SimpleBanner variant="launch" message="Bulk cargo bookings are live." link="/changelog/bulk-cargo-bookings" linkText="See what’s new" />

<SimpleBanner variant="info" message="Orbit API 1.4 is out." />

<SimpleBanner variant="success" message="All systems are operational." link="/page/status" linkText="Mission Control" />

<SimpleBanner variant="warn" message="The launch weather endpoint stops working on March 1, 2027." link="/reference/getlaunchweather" linkText="Migrate" dismissible="true" />

<SimpleBanner variant="error" message="Legacy v0 booking endpoints are gone." link="/changelog/v0-bookings-removed" linkText="Details" />

## 在网站页眉中 {#in-the-site-header}

使用 `placement="header"` 时，当此页面处于打开状态，横幅会横跨在网站顶部。抬头看看：它现在就在那里。

<SimpleBanner placement="header" variant="launch" message="This banner lives in the site header while you’re on this page." dismissible="true" />

## 使用方法 {#use-it}

```mdx
<SimpleBanner variant="warn" message="Maintenance on Saturday." link="/page/status" linkText="Status" dismissible="true" />
```

| 属性                 | 取值                                           | 说明                           |
| :----------------- | :------------------------------------------- | :--------------------------- |
| `message`          | 文本                                           | 横幅显示的内容                      |
| `variant`          | `info`, `success`, `warn`, `error`, `launch` | 样式                           |
| `icon`             | Emoji                                        | 替换变体的图标                      |
| `link`, `linkText` | URL、文本                                       | 末尾的可选链接                      |
| `placement`        | `inline`, `header`                           | 显示位置。`header` 会将其置于网站顶部横跨显示。 |
| `dismissible`      | `true`                                       | 添加关闭按钮。在本次访问的剩余时间内它将保持关闭状态。  |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 页眉横幅会在页面打开时添加，并在读者离开该页面时移除。
  - 传递了 `isHeader`、`bannerColor` 和 `bannerTextColor` 的旧版页面仍可正常工作。
</Accordion>
