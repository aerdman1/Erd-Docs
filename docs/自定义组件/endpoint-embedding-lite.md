---
title: Endpoint 标签
excerpt: 读取 API 定义的 Endpoint 预览。
deprecated: false
hidden: false
icon: fad fa-link
metadata:
  robots: index
---
在句子中提及某个 endpoint，读者即可悬停其上或通过 Tab 键切换至该 endpoint 以查看预览。为其指定一个 `operationId`，它就会从 API 定义中读取方法、标题和描述，因此内容永远不会过时。

使用 <EndpointEmbedLite operationId="listLaunches" /> 查找发射任务，使用 <EndpointEmbedLite operationId="createBooking" /> 进行预订，然后等待 <EndpointEmbedLite operationId="bookingConfirmed" />。

## 以卡片形式 {#as-a-card}

<EndpointEmbedLite operationId="uploadManifest" displayMode="card" />

<EndpointEmbedLite operationId="getLaunchWeather" displayMode="card" />

已弃用的 endpoint 会自动被标记。

## 使用方法 {#use-it}

```mdx
Book it with <EndpointEmbedLite operationId="createBooking" />.

<EndpointEmbedLite operationId="uploadManifest" displayMode="card" />
```

| 属性                                           | 取值                      | 说明                            |
| :------------------------------------------- | :---------------------- | :---------------------------- |
| `operationId`                                | 文本                      | 要显示的 endpoint 或 webhook       |
| `displayMode`                                | `popup`, `chip`, `card` | 带预览的标签、普通标签或完整卡片              |
| `spec`                                       | 文件名                     | 要读取的 API 定义。默认为 `orbit.yaml`。 |
| `linkText`                                   | 文本                      | 替换标签的文本                       |
| `method`, `endpoint`, `title`, `description` | 文本                      | 设置这些项以跳过 API 定义               |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 它会从 hub 的 `/openapi/orbit.yaml` 读取 API 定义，每个页面读取一次。
  - 每个标签都会链接到 API Reference 中该 endpoint 的页面。
</Accordion>
