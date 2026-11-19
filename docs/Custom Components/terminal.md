---
title: 终端
excerpt: 自动键入内容的 CLI 会话。
deprecated: false
hidden: false
icon: fad fa-terminal
metadata:
  robots: index
---
显示一个在滚动到可视区域时播放的命令行会话。**复制**仅提取命令， **↻** 则重新播放。

<Terminal title="orbit — zsh" script="$ npm install -g @erdman/orbit-cli\nadded 1 package in 2s\n$ orbit login\n✔ Logged in as dana@pixelowl.space\n$ orbit launches list --min-capacity 4\n→ lch_9Kd4Mw  Polaris Run  kestrel  SSO  120 kg free\n$ orbit book lch_9Kd4Mw --payload ./pixel-owl.json\n✔ Booked bkg_4Fh8Qp (pending manifest review)" />

Orbit CLI 和 Orbit 的其余部分一样，都是虚构的。

## 使用方法 {#use-it}

使用 `\n` 分隔各行。以 `$ ` 开头的行是命令。以 ✔、✖、⚠、→ 或 # 开头的输出行会显示各自的颜色。

```mdx
<Terminal title="orbit — zsh" script="$ orbit login\n✔ Logged in\n$ orbit launches list" />
```

| 属性        | 取值      | 作用                |
| :-------- | :------ | :---------------- |
| `script`  | 文本      | 会话内容，每行用 `\n` 分隔  |
| `title`   | 文本      | 窗口标题              |
| `speed`   | 毫秒      | 每个字符的键入延迟。默认为 28。 |
| `animate` | `false` | 一次性显示全部内容         |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 它会等待滚动到可视区域，然后开始键入。
  - 对于开启了减弱动态效果的读者，整个会话会一次性显示。
</Accordion>
