---
title: API 密钥卡片
excerpt: 向已登录读者显示他们自己的 API 密钥。
deprecated: false
hidden: false
icon: fad fa-key
metadata:
  robots: index
---
已登录的读者可以看到自己的密钥，该密钥在主动显示前处于遮蔽状态。未登录的读者会看到 **登录** 按钮，任何人都可以使用演示密钥预览此卡片。

<ApiKeyCard />

## 密钥的来源 {#where-the-key-comes-from}

每个自定义组件都可以将已登录读者的登录数据作为 `user` 读取。当登录流程通过 JWT、SAML 或 Personalized Docs webhook 发送 `apiKey` 字段时，卡片便会显示它。相同的登录数据还会填充到 [API 参考](/reference/listlaunches) 中的 Try It。

```jsx
const key = 'apiKey' in user ? user.apiKey : '';
```

<Callout icon="⚠️" theme="warn">
  使用 `in` 检查字段是否存在。`user` 上缺失的字段会返回该字段的大写名称，而不是 `undefined`。
</Callout>

## 使用方法 {#use-it}

```mdx
<ApiKeyCard field="apiKey" />
```

| 属性      | 值  | 作用                        |
| :------ | :- | :------------------------ |
| `field` | 文本 | 用于保存密钥的登录字段。默认为 `apiKey`。 |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 无需获取任何数据：密钥已存在于已登录读者的页面上，且仅其本人可见。
  - **复制** 功能在 ReadMe 的编辑器预览中也同样有效。
</Accordion>
