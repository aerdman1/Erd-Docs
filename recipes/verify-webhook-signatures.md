---
title: 验证 Webhook 签名
description: 在对其进行处理之前，请先确认 Webhook 确实来自 Orbit。
hidden: false
recipe:
  color: '#7B3FF2'
  icon: 🔏
---
```javascript Node.js
import express from 'express';
import crypto from 'node:crypto';

const app = express();

// Keep the raw bytes: the signature covers the body exactly as sent
app.post('/hooks/orbit', express.raw({ type: 'application/json' }), (req, res) => {
  const header = req.get('Orbit-Signature'); // t=1763391852,v1=5f2b…
  const { t, v1 } = Object.fromEntries(header.split(',').map(p => p.split('=')));

  // Reject anything older than five minutes
  if (Math.abs(Date.now() / 1000 - Number(t)) > 300) return res.sendStatus(400);

  const expected = crypto
    .createHmac('sha256', process.env.ORBIT_WEBHOOK_SECRET)
    .update(`${t}.${req.body}`)
    .digest('hex');
  if (!crypto.timingSafeEqual(Buffer.from(expected), Buffer.from(v1))) return res.sendStatus(400);

  const event = JSON.parse(req.body);
  console.log(event.type, event.data.id); // booking.confirmed bkg_4Fh8Qp
  res.sendStatus(204);
});

app.listen(3000);
```

# 读取原始请求体

<!-- javascript@6-7 -->

签名逐字节覆盖请求体，因此请直接获取原始请求体。解析 JSON 并重新序列化会改变字节。

# 拆分请求头

<!-- javascript@8-9 -->

`Orbit-Signature` 包含 Unix 时间戳 `t` 和签名 `v1`。

# 检查时间戳

<!-- javascript@11-12 -->

拒绝超过五分钟的事件，以防旧请求被重放。

# 比对签名

<!-- javascript@14-18 -->

使用您的 Webhook 密钥对 `t.body` 进行签名，并在恒定时间内进行比对。

# 处理事件

<!-- javascript@20-22 -->

在十秒内返回任意 `2xx`。否则 Orbit 将进行退避重试，最多重试五次。