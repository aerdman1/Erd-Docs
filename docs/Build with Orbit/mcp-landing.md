---
title: AI 与 MCP
excerpt: 用通俗易懂的英语提出关于 Orbit 的问题，或将这些文档接入您的 AI 工具。
deprecated: false
hidden: false
icon: fad fa-sparkles
metadata:
  robots: index
---
本文档中心专为人类**以及** AI 阅读而构建。此页面上的内容均无需自定义代码：一切都是 ReadMe 的一部分。

## 询问 AI {#ask-ai}

点击页眉中的**询问 AI**并提出类似 _“如何预订前往太阳同步轨道的立方星？”_ 的问题。答案提取自这些指南和 API 参考，并附有指向所引用页面的链接。

## 通过 MCP 连接您的 AI 工具 {#connect-your-ai-tools-with-mcp}

每个 ReadMe 文档中心都可以运行**MCP 服务器**。将其连接至 Claude、Cursor 或其他 MCP 客户端，客户端便可在为您编写集成的同时搜索这些文档并读取 Orbit API 定义。

选择您的客户端：

<Tabs>
  <Tab title="Claude Code" icon="fa-terminal">
    ```shell
    claude mcp add --transport http orbit https://erdman.readme.io/mcp
    ```
  </Tab>

  <Tab title="Cursor" icon="fa-arrow-pointer">
    ```json ~/.cursor/mcp.json
    {
      "mcpServers": {
        "orbit": { "url": "https://erdman.readme.io/mcp" }
      }
    }
    ```
  </Tab>

  <Tab title="VS Code" icon="fa-code">
    ```json .vscode/mcp.json
    {
      "servers": {
        "orbit": { "type": "http", "url": "https://erdman.readme.io/mcp" }
      }
    }
    ```
  </Tab>
</Tabs>

每个页面顶部的**复制页面**菜单都提供了相同的选项，均可一键完成。

### 该服务器支持的功能 {#what-the-server-can-do}

| 工具                   | 功能说明                                 |
| :------------------- | :----------------------------------- |
| `search`, `fetch`    | 搜索这些指南并阅读任意页面                        |
| `list-endpoints`     | 列出所有 Orbit 端点                        |
| `search-endpoints`   | 按关键词、参数或字段查找端点                       |
| `get-endpoint`       | 读取单个端点的参数、模式与认证信息                    |
| `execute-request`    | 使用用户的密钥实际调用 API                      |
| `plan-orbit-booking` | 一个**自定义工具**：按顺序排列的预订步骤，在仪表盘中以零代码方式编写 |

## 面向 LLM 的文档 {#docs-for-llms}

| 内容                   | 位置                                               |
| :------------------- | :----------------------------------------------- |
| 所有页面的索引              | [`/llms.txt`](https://erdman.readme.io/llms.txt) |
| 以 Markdown 格式呈现的任意页面 | 在页面 URL 后添加 `.md`，例如 `/docs/quickstart.md`       |
| Orbit API 定义         | 显示在 [API 参考](/reference/listlaunches) 中的各个端点处    |

<Callout icon="✨" theme="info">
  试一试：将 `https://erdman.readme.io/docs/quickstart.md` 粘贴到您的 AI 工具中，并让它用您的语言编写预订脚本。
</Callout>

<Accordion title="本页面的构建方式" icon="fa-wand-magic-sparkles">
  - **选项卡**，包含针对每个 MCP 客户端的代码块
  - 文档中心的**MCP 服务器**（在设置中开启），以及在仪表盘中添加的**自定义 MCP 工具**
  - **询问 AI**、`llms.txt` 以及 `.md` 页面导出均为文档中心功能，可在设置中开启
  - 一个**表格**和一个 **info** 标注框
</Accordion>
