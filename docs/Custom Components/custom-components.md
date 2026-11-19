---
title: 自定义组件
excerpt: 用 MDX 编写的 React 组件，可像内置区块一样在任意页面中使用。
deprecated: false
hidden: false
icon: fad fa-puzzle-piece
metadata:
  robots: index
---
内置区块适用于大多数页面。当你需要它们无法实现的功能时，可以编写**自定义组件**：即 MDX 文件中的 React 组件，保存在控制台项目下的 **Components** 中。之后，任何页面都可以像使用 Callout 或 Tabs 一样，通过标签来使用它。

本节中的每个组件都是这样的文件。每个页面都会实时展示其效果，并介绍具体的使用方法。

<Cards columns="3">
  <Card title="倒计时" href="/docs/launch-countdown" icon="fa-timer" iconColor="#7B3FF2" badge="新">
    以读者所在时区实时运行的倒计时时钟。
  </Card>

  <Card title="Payload 计算器" href="/docs/payload-calculator" icon="fa-calculator" iconColor="#2F7BF5" badge="新">
    估算 payload 费用并获取精确的 API 请求。
  </Card>

  <Card title="Orbit 可视化" href="/docs/orbit-viz" icon="fa-earth-americas" iconColor="#19C3F5" badge="新">
    一个可供探索的动态轨道图。
  </Card>

  <Card title="终端" href="/docs/terminal" icon="fa-terminal" iconColor="#12B76A" badge="新">
    自动键入内容的 CLI 会话。
  </Card>

  <Card title="API Key 卡片" href="/docs/api-key-card" icon="fa-key" iconColor="#F79009" badge="新">
    向已登录读者展示他们自己的密钥。
  </Card>

  <Card title="更新日志 Feed" href="/docs/changelog-feed" icon="fa-rss" iconColor="#F04438" badge="新">
    在任意页面展示最新的更新日志文章。
  </Card>

  <Card title="步骤条" href="/docs/simple-stepper" icon="fa-list-ol">
    可点击切换的步骤，或垂直时间线。
  </Card>

  <Card title="横幅" href="/docs/simple-banner" icon="fa-flag">
    内联或全站公告。
  </Card>

  <Card title="模态框" href="/docs/content-modal" icon="fa-window-restore">
    点击即可查看可选详情。
  </Card>

  <Card title="端点标签" href="/docs/endpoint-embedding-lite" icon="fa-link">
    读取 API 定义的端点预览。
  </Card>

  <Card title="端点选择器" href="/docs/endpoint-picker" icon="fa-list-tree">
    通过一个下拉菜单浏览所有端点。
  </Card>

  <Card title="页内查找" href="/docs/page-searching" icon="fa-magnifying-glass">
    边输入边搜索并高亮显示。
  </Card>

  <Card title="客户评价" href="/docs/quotes" icon="fa-quote-left">
    轮播展示的引言。
  </Card>

  <Card title="SDK 浏览器" href="/docs/sdk-explorer" icon="fa-cube">
    通过类型定义浏览软件包的 API。
  </Card>
</Cards>

## 它们的构建方式 {#how-theyre-built}

<Columns layout="auto">
  <Column>
    **每个组件一个文件**

    每个组件都是一个 MDX 文件，并导出一个与文件名同名的 React 组件。
  </Column>

  <Column>
    **纯字符串 props**

    页面以字符串形式传递 props，例如 `vertical="true"`，因此在编辑器中编写非常轻松。
  </Column>

  <Column>
    **遵循 hub 主题**

    颜色来自 hub 自带的主题变量，因此每个组件都能适配浅色和深色模式。
  </Column>
</Columns>

<Callout icon="📘" theme="info">
  自定义组件使用 React 在读者的浏览器中运行。它们可以读取已登录读者的登录数据、从 hub 获取内容，并使用任何浏览器 API。有关示例，请参见 [API Key Card](/docs/api-key-card)。
</Callout>
