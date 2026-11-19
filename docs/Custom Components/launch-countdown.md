---
title: 发射倒计时
excerpt: 下一个发射窗口的实时 T-minus 倒计时时钟。
deprecated: false
hidden: false
icon: fad fa-timer
metadata:
  robots: index
---
每秒跳动一次的倒计时，显示任务的发射/中止状态，并以读者所在时区显示发射窗口。

<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" pad="LC-39X" />

## 暂停与取消 {#holds-and-scrubs}

设置 `status` 以显示暂停或取消：

<LaunchCountdown mission="Night Heron" vehicle="wren" orbit="LEO" status="hold" />

## 使用方法 {#use-it}

```mdx
<LaunchCountdown mission="Polaris Run" vehicle="kestrel" orbit="SSO" at="2026-12-09T03:41:00Z" />
```

| 属性        | 取值                       | 说明                            |
| :-------- | :----------------------- | :---------------------------- |
| `mission` | 文本                       | 任务名称                          |
| `vehicle` | 文本                       | 火箭                            |
| `orbit`   | 文本                       | 目的地                           |
| `pad`     | 文本                       | 发射台（可选）                       |
| `at`      | ISO 8601 时间              | 窗口开启时间。如果不提供，时钟将倒计时至下周的下一个窗口。 |
| `status`  | `go`, `hold`, `scrubbed` | 状态指示灯。默认为 `go`。               |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 时钟在读者的浏览器中运行，因此窗口时间始终处于其所在时区。
  - 时间过去后，它会切换为**升空**。
  - 对于开启了减弱动态效果的读者，火箭和状态指示灯将保持静止。
</Accordion>
