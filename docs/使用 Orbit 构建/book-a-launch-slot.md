---
title: 预订发射档期
excerpt: 完整的预订流程，从寻找发射到确认档期。
deprecated: false
hidden: false
icon: fad fa-box-taped
metadata:
  robots: index
---
预订分为四个步骤。点击浏览各步骤，然后阅读下方的详细说明。如果您更倾向于查看代码，可以参考 Recipe：

<Recipe slug="book-your-first-launch-slot" title="预订您的首个发射位" />

<SimpleStepper>
  <SimpleStep header="1. 寻找发射任务">
    列出剩余运载能力足以承载您有效载荷的发射任务。
  </SimpleStep>

  <SimpleStep header="2. 预订发射位">
    创建预订。其初始状态为待处理。
  </SimpleStep>

  <SimpleStep header="3. 上传货物清单">
    以 PDF 格式附上已签署的货物清单。
  </SimpleStep>

  <SimpleStep header="4. 等待确认">
    booking.confirmed Webhook 会通知您预订已最终确认。
  </SimpleStep>
</SimpleStepper>

## 开始之前 {#before-you-start}

- [x] 您已拥有 API 密钥（[身份验证](/docs/authentication)）
- [x] 您已知晓有效载荷的质量与目标轨道
- [ ] 您的 <Glossary>manifest</Glossary> 已签署并保存为 PDF
- [ ] 您已准备好 Webhook 端点（[Webhooks](/docs/webhooks)）

## 先进行估价 {#price-it-first}

查看哪些运载工具可以承载您的有效载荷及其费用。计算器会自动为您生成预订请求：

<PayloadCalculator />

## 1. 寻找发射任务 {#1-find-a-launch}

调用 <EndpointEmbedLite operationId="listLaunches" />，将 `min_capacity_kg` 设置为您有效载荷的质量。如果您的有效载荷需要特定运载工具，可按 `vehicle` 进行筛选。

## 2. 预订发射位 {#2-book-the-slot}

调用 <EndpointEmbedLite operationId="createBooking" />。`payload.type` 字段决定了哪些其他字段是必填项：

<Tabs>
  <Tab title="卫星" icon="fa-satellite">
    ```json
    {
      "launch_id": "lch_9Kd4Mw",
      "payload": {
        "type": "satellite",
        "name": "Pixel Owl 3U",
        "mass_kg": 4,
        "target_orbit": "sso",
        "deploy_altitude_km": 525
      },
      "insurance": "standard"
    }
    ```
  </Tab>

  <Tab title="散装货物" icon="fa-boxes-stacked">
    ```json
    {
      "launch_id": "lch_7Hq2Zr",
      "payload": {
        "type": "bulk_cargo",
        "name": "Hydroponics resupply",
        "mass_kg": 820,
        "pressurized": true,
        "hazmat_class": "none"
      },
      "insurance": "premium"
    }
    ```
  </Tab>
</Tabs>

<Callout icon="📘" theme="info">
  ### 重试是安全的 {#retries-are-safe}

  每次发起新预订时，请在 `Idempotency-Key` 请求头中发送一个新的 UUID。如果网络中断且您使用相同的密钥进行重试，Orbit 将返回原始预订，而不会重复预订。
</Callout>

## 3. 上传货物清单 {#3-upload-the-manifest}

以 `multipart/form-data` 格式将已签署的 PDF 发送至[上传货物清单](/reference/uploadmanifest)：

```javascript upload-manifest.js
import fs from 'node:fs';

const form = new FormData();
form.append('file', new Blob([fs.readFileSync('manifest.pdf')]), 'manifest.pdf');
form.append('signed_by', 'Dana Whitfield');

await fetch(`https://api.us-east.orbit.erdman.example/v1/bookings/${bookingId}/manifest`, {
  method: 'POST',
  headers: { 'X-Orbit-Key': process.env.ORBIT_KEY },
  body: form,
});
```

## 4. 等待确认 {#4-wait-for-confirmation}

Orbit 会在一个工作日内审核货物清单。审核通过后，预订状态将变更为 `confirmed`，并且您会收到一个 [booking.confirmed](/reference/bookingconfirmed) Webhook。

<Accordion title="此页面的构建方式" icon="fa-wand-magic-sparkles">
  - 一个**自定义组件**：`SimpleStepper`，使用 MDX 编写并随项目一同存储
  - 一个 **Recipe** 嵌入组件：可在原位展开的分步代码演练
  - [有效载荷计算器](/docs/payload-calculator)与[端点标签](/docs/endpoint-embedding-lite)，另外两个**自定义组件**
  - 核对清单中的一个 **Glossary** 术语
  - 使用 Markdown 任务列表语法的**核对清单**
  - 包含每种 `oneOf` 有效载荷类型 JSON 示例的 **Tabs**
  - 一个**带有文件名的代码块**作为其标题
  - 一个 **info** 提示框
</Accordion>
