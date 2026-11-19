---
title: 更新日志动态
excerpt: 在任意页面上展示最新的更新日志文章。
deprecated: false
hidden: false
icon: fad fa-rss
metadata:
  robots: index
---
将更新日志文章拉取到任意页面。它会读取 Hub 自身的 RSS 源，因此无需编辑此页面，新文章就会显示在这里。支持按类型筛选或搜索。

<RSS limit="10" />

## 紧凑 {#compact}

简短列表适用于着陆页或欢迎页：

<RSS compact="true" limit="3" title="最新变更" />

## 使用方法 {#use-it}

```mdx
<RSS limit="10" />

<RSS compact="true" limit="3" title="Latest changes" />
```

| 属性        | 取值                                                    | 作用                          |
| :-------- | :---------------------------------------------------- | :-------------------------- |
| `limit`   | 数字                                                    | 要显示的文章数量。默认为 20。            |
| `compact` | `true`                                                | 显示简短列表而非时间线                 |
| `title`   | 文本                                                    | 紧凑列表的标题                     |
| `filters` | `false`                                               | 隐藏类型筛选器和搜索                  |
| `type`    | `added`, `improved`, `fixed`, `deprecated`, `removed` | 初始筛选为单一类型                   |
| `url`     | 路径                                                    | 其他订阅源。默认为 `/changelog.rss`。 |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 该订阅源会在读者的浏览器中缓存五分钟。
  - 类型标签来自更新日志中每篇文章对应的类型。
</Accordion>
