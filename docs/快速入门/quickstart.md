---
title: 快速入门
excerpt: 在大约五分钟内发起您的第一个 Orbit 请求。
deprecated: false
hidden: false
icon: fad fa-rocket
metadata:
  robots: index
---
读完本页后，您将能够列出即将进行的发射任务并预订测试有效载荷。

## 1. 获取 API 密钥 {#1-get-an-api-key}

登录 Orbit，打开**账户 → API 密钥**并创建一个密钥。测试密钥以 `ok_test_` 开头，且绝不会向您收费。

<Callout icon="🔑" theme="warn">
  请将机密密钥保存在您的服务器上。任何拥有您密钥的人都可以使用您的账户预订发射任务。
</Callout>

当您登录此中心后，[API 参考](/reference/listlaunches)会自动为您填入密钥，因此 **立即尝试！** 可以直接使用。

## 2. 寻找有空位的发射任务 {#2-find-a-launch-with-room}

查询仍有至少 4 kg 剩余运力的发射任务：

```shell cURL
curl "https://api.us-east.orbit.erdman.example/v1/launches?min_capacity_kg=4" \
  -H "X-Orbit-Key: $ORBIT_KEY"
```
```javascript Node.js
const res = await fetch('https://api.us-east.orbit.erdman.example/v1/launches?min_capacity_kg=4', {
  headers: { 'X-Orbit-Key': process.env.ORBIT_KEY },
});
const { data } = await res.json();

for (const launch of data) {
  console.log(`${launch.name}: ${launch.capacity.available_kg} kg free`);
}
```
```python Python
import os
import requests

res = requests.get(
    "https://api.us-east.orbit.erdman.example/v1/launches",
    params={"min_capacity_kg": 4},
    headers={"X-Orbit-Key": os.environ["ORBIT_KEY"]},
)
for launch in res.json()["data"]:
    print(f'{launch["name"]}: {launch["capacity"]["available_kg"]} kg free')
```

您将收到一页发射任务列表，按时间从近到远排序：

```json
{
  "data": [
    {
      "id": "lch_9Kd4Mw",
      "name": "Polaris Run",
      "vehicle": "wren",
      "status": "go",
      "capacity": { "total_kg": 900, "available_kg": 120 },
      "target_orbit": "sso"
    }
  ],
  "has_more": true,
  "next_cursor": "Y3Vyc29yOjI="
}
```

## 3. 预订测试有效载荷 {#3-book-a-test-payload}

在您找到的发射任务中预订一颗 4 kg 的立方星。`Idempotency-Key` 请求头可确保该请求能够安全地重试。

```shell cURL
curl -X POST "https://api.us-east.orbit.erdman.example/v1/bookings" \
  -H "X-Orbit-Key: $ORBIT_KEY" \
  -H "Content-Type: application/json" \
  -H "Idempotency-Key: $(uuidgen)" \
  -d '{
    "launch_id": "lch_9Kd4Mw",
    "payload": { "type": "satellite", "name": "Pixel Owl 3U", "mass_kg": 4, "target_orbit": "sso" }
  }'
```
```javascript Node.js
import { randomUUID } from 'node:crypto';

const res = await fetch('https://api.us-east.orbit.erdman.example/v1/bookings', {
  method: 'POST',
  headers: {
    'X-Orbit-Key': process.env.ORBIT_KEY,
    'Content-Type': 'application/json',
    'Idempotency-Key': randomUUID(),
  },
  body: JSON.stringify({
    launch_id: 'lch_9Kd4Mw',
    payload: { type: 'satellite', name: 'Pixel Owl 3U', mass_kg: 4, target_orbit: 'sso' },
  }),
});
console.log(await res.json()); // status: "pending"
```

预订返回的状态为 `pending`。在 Orbit 审核您的货物清单后，状态将变为 `confirmed`。

## 更喜欢使用命令行？ {#prefer-the-command-line}

使用 Orbit CLI 进行相同的预订：

<Terminal title="orbit — zsh" script="$ npm install -g @erdman/orbit-cli\nadded 1 package in 2s\n$ orbit launches list --min-capacity 4\n→ lch_9Kd4Mw  Polaris Run  kestrel  SSO  120 kg free\n$ orbit book lch_9Kd4Mw --payload ./pixel-owl.json\n✔ Booked bkg_4Fh8Qp (pending manifest review)" />

<Callout icon="🎉" theme="okay">
  ### 您已成功预订首次发射 {#you-booked-your-first-launch}

  接下来，[上传货物清单](/docs/book-a-launch-slot)并[设置 webhook](/docs/webhooks)，以便在预订确认时收到通知。
</Callout>

<Accordion title="本页面的构建方式" icon="fa-wand-magic-sparkles">
  - 带编号的**标题**，同时用于生成右侧的目录
  - **代码选项卡**：连续的代码块，每个都带有语言和选项卡名称，会合并为一个带选项卡的代码块
  - 带有 JSON 语法高亮的普通**代码块**
  - 采用警告和成功主题的**提示框**
  - 指向其他指南及**API 参考**的链接
  - 用于逐字打出 CLI 会话的 [终端](/docs/terminal) **自定义组件**
</Accordion>
