---
title: 错误与速率限制
excerpt: Orbit 错误的含义，以及如何避免超出速率限制。
deprecated: false
hidden: false
icon: fad fa-triangle-exclamation
metadata:
  robots: index
---
Orbit 使用标准 HTTP 状态码。每个错误响应体都是一个 [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457) _问题详&#x60C5;_&#x5BF9;象，因此只需一个处理程序即可覆盖所有错误：

```json
{
  "type": "https://erdman.readme.io/docs/errors-and-rate-limits#launch-full",
  "title": "Launch is full",
  "status": 409,
  "detail": "Polaris Run has 120 kg free and this payload is 820 kg."
}
```

## 状态码 {#status-codes}

|  状态码  | 含义            | 是否重试？                |
| :---: | :------------ | :------------------- |
| `400` | 请求格式错误        | 否，请修正请求              |
| `401` | API 密钥缺失或无效   | 否                    |
| `404` | 不存在具有该 ID 的资源 | 否                    |
| `409` | 本次发射已满载       | 是，更换其他发射任务           |
| `422` | 有效载荷无法到达目标轨道  | 是，改用更大的运载火箭          |
| `429` | 已达到速率限制       | 是，在 `Retry-After` 之后 |
| `5xx` | 我们这边的服务出现故障   | 是，采用退避策略重试           |

## 常见错误 {#common-errors}

### 未授权 {#unauthorized}

<Callout icon="❗️" theme="error">
  `401` 表示缺少 `X-Orbit-Key` 标头，或者密钥已轮换。生产密钥不适用于测试数据，测试密钥也不适用于生产数据。
</Callout>

### 发射已满载 {#launch-full}

<Callout icon="⚠️" theme="warn">
  `409` 表示有人在你之前预订了最后几千克载荷。请携带 `min_capacity_kg` 调用[列出发射任务](/reference/listlaunches)以查找其他发射任务。
</Callout>

### 超出 Delta-v {#delta-v-exceeded}

<Callout icon="🚀" theme="default">
  `422` 表示该运载火箭无法将该质量送入该轨道\[^1]。`wren` 送入 GEO 的运力约为 150 kg，因此请将较重的有效载荷转至 `kestrel-heavy`。
</Callout>

## 速率限制 {#rate-limits}

每个密钥每分钟可发起 120 次请求。每个响应都会告知你当前的配额状态：

| 标头                      | 示例    | 含义                      |
| :---------------------- | :---- | :---------------------- |
| `X-RateLimit-Remaining` | `118` | 此一分钟窗口内剩余的请求次数          |
| `Retry-After`           | `12`  | 需要等待的秒数（仅出现在 `429` 响应中） |

<Callout icon="📘" theme="info">
  需要更多配额？**Fleet** 方案将上限提高到每分钟 1,200 次请求。请通过[获取账户用量](/reference/getusage)查看当前的用量情况。
</Callout>

<Callout icon="👍" theme="okay">
  Webhook 不计入速率限制。建议使用 Webhook 代替轮询发射状态。
</Callout>

[^1]: 火箭方程是不容妥协的，哪怕对一家虚构的公司也是如此。

<Accordion title="本页面的构建方式" icon="fa-wand-magic-sparkles">
  - 涵盖所有主题的**提示框**：error、warning、default、info 和 success
  - API 参考文档通过锚点（`#launch-full`）链接到的 3 级**标题**
  - 带有居中列的**表格**
  - 一个**脚注**
  - 正文文本中的斜体、粗体和行内代码
</Accordion>
