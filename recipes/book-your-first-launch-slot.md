---
title: 预订您的首个发射槽位
description: 寻找有足够载荷空间的发射任务并进行预订，只需约 20 行代码。
hidden: false
recipe:
  color: '#2F7BF5'
  icon: 🚀
---
```javascript Node.js
const BASE = 'https://api.us-east.orbit.erdman.example/v1';
const headers = { 'X-Orbit-Key': process.env.ORBIT_KEY, 'Content-Type': 'application/json' };

// Find a launch with room for a 4 kg CubeSat
const res = await fetch(`${BASE}/launches?status=scheduled&min_capacity_kg=4`, { headers });
const { data: launches } = await res.json();
const launch = launches[0];

// Book the slot. The Idempotency-Key makes retries safe.
const booking = await fetch(`${BASE}/bookings`, {
  method: 'POST',
  headers: { ...headers, 'Idempotency-Key': crypto.randomUUID() },
  body: JSON.stringify({
    launch_id: launch.id,
    payload: { type: 'satellite', name: 'Pixel Owl 3U', mass_kg: 4, target_orbit: 'sso' },
  }),
}).then(r => r.json());

console.log(booking.id, booking.status); // bkg_4Fh8Qp pending
```

```python Python
import os, uuid, requests

BASE = "https://api.us-east.orbit.erdman.example/v1"
headers = {"X-Orbit-Key": os.environ["ORBIT_KEY"]}

# Find a launch with room for a 4 kg CubeSat
res = requests.get(f"{BASE}/launches", params={"status": "scheduled", "min_capacity_kg": 4}, headers=headers)
launch = res.json()["data"][0]

# Book the slot. The Idempotency-Key makes retries safe.
booking = requests.post(
    f"{BASE}/bookings",
    headers={**headers, "Idempotency-Key": str(uuid.uuid4())},
    json={
        "launch_id": launch["id"],
        "payload": {"type": "satellite", "name": "Pixel Owl 3U", "mass_kg": 4, "target_orbit": "sso"},
    },
).json()

print(booking["id"], booking["status"])  # bkg_4Fh8Qp pending
```

```json Response Example
{
  "id": "bkg_4Fh8Qp",
  "launch_id": "lch_9Kd4Mw",
  "status": "pending",
  "payload": {
    "type": "satellite",
    "name": "Pixel Owl 3U",
    "mass_kg": 4,
    "target_orbit": "sso"
  },
  "insurance": "standard",
  "created_at": "2026-11-17T15:04:12Z"
}
```

# 配置客户端

<!-- javascript@1-2 -->
<!-- python@1-4 -->

每个请求都需要在 `X-Orbit-Key` 请求头中包含您的 API 密钥。请将其保存在环境变量中，切勿写在代码中。

# 查找发射任务

<!-- javascript@4-7 -->
<!-- python@6-8 -->

[列出发射任务](/reference/listlaunches)并将 `min_capacity_kg` 设置为您的载荷质量。系统仅会返回具有足够空闲空间的发射任务。

# 预订槽位

<!-- javascript@9-17 -->
<!-- python@10-18 -->

在该发射任务上[预订载荷槽位](/reference/createbooking)。`payload.type` 决定哪些字段为必填项：卫星需要提供 `target_orbit`。

# 检查结果

<!-- javascript@19 -->
<!-- python@20 -->

新预订的初始状态为 `pending`。接下来上传载荷清单，然后等待 `booking.confirmed` webhook。