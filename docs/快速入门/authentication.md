---
title: 身份验证
excerpt: 使用 API 密钥进行身份验证，或在代表团队操作时使用 OAuth 2.0。
deprecated: false
hidden: false
icon: fad fa-key
metadata:
  robots: index
---
每个 Orbit 请求都经过身份验证。请选择适合您集成运行方式的方法。

已登录？您的密钥就在这里：

<ApiKeyCard />

<Tabs>
  <Tab title="API 密钥" icon="fa-key">
    在 `X-Orbit-Key` 请求头中发送您的密钥。这是最快的入门方式，适用于脚本和后端服务。

    ```shell
    curl "https://api.us-east.orbit.erdman.example/v1/account/usage" \
      -H "X-Orbit-Key: ok_test_4eC39HqLyjWDarjtT1zdp7dc"
    ```

    | 前缀         | 模式 | 从您的银行卡扣款 |
    | :--------- | :- | :------- |
    | `ok_test_` | 测试 | 从不       |
    | `ok_live_` | 实时 | 是        |
  </Tab>

  <Tab title="OAuth 2.0" icon="fa-shield-check">
    当您的平台为团队预订发射服务时，请使用**客户端凭据**流程。使用您的客户端 ID 和密钥换取短期令牌：

    ```shell
    curl -X POST "https://auth.orbit.erdman.example/oauth/token" \
      -d grant_type=client_credentials \
      -d client_id=$ORBIT_CLIENT_ID \
      -d client_secret=$ORBIT_CLIENT_SECRET \
      -d scope="bookings:read bookings:write"
    ```

    然后将其作为 Bearer 令牌发送：`Authorization: Bearer <token>`。令牌有效期为一小时。
  </Tab>
</Tabs>

## 权限范围 {#scopes}

OAuth 令牌只能访问其权限范围允许的内容。API 密钥则拥有所有权限范围。

| 权限范围             | 允许您              |
| :--------------- | :--------------- |
| `bookings:read`  | 列出并读取预订          |
| `bookings:write` | 创建、修改和取消预订       |
| `telemetry:read` | 读取飞行中有效载荷的实时遥测数据 |

<Callout icon="❗️" theme="error">
  ### 切勿将密钥发布到浏览器或应用程序中 {#never-ship-a-secret-key-to-a-browser-or-an-app}

  前端代码中的密钥任何人都可以读取。如果密钥泄露，请在**账户 → API 密钥**中进行轮换。旧密钥将立即失效。
</Callout>

<OrbitHelp />

<Accordion title="本页面的构建方式" icon="fa-wand-magic-sparkles">
  - 带有 Font Awesome 图标的**选项卡**，每个选项卡包含代码和一个表格
  - 两个 Markdown **表格**
  - 一个**错误**提示框
  - [API 密钥卡片](/docs/api-key-card)，一个用于读取已登录读者自身密钥的**自定义组件**
  - 底部的帮助框是**可复用内容**：同一个代码片段，在一处编辑，在多个页面中展示
  - API 参考文档从 OpenAPI 文件的 `securitySchemes` 中读取相同的这两种身份验证方法
</Accordion>
