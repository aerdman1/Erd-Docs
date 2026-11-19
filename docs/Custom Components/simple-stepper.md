---
title: 步骤条
excerpt: 可点击切换的步骤，或垂直时间线。
deprecated: false
hidden: false
icon: fad fa-list-ol
metadata:
  robots: index
---
将任务分解为读者可以点击浏览的各个步骤。方向键也同样支持，且每个圆点均可直接跳转至对应步骤。

<SimpleStepper>
  <SimpleStep header="查找发射">
    列出具有足够剩余运力来搭载您有效载荷的发射任务。
  </SimpleStep>

  <SimpleStep header="预订槽位">
    创建预订。初始状态为待处理。
  </SimpleStep>

  <SimpleStep header="上传舱单">
    以 PDF 格式附加已签署的货物舱单。
  </SimpleStep>

  <SimpleStep header="等待确认">
    booking.confirmed webhook 会通知您预订已最终确认。
  </SimpleStep>
</SimpleStepper>

## 以时间线形式展示 {#as-a-timeline}

添加 `vertical="true"` 即可一次性显示所有步骤：

<SimpleStepper vertical="true">
  <SimpleStep header="T−24 小时">
    有效载荷已密封在整流罩内。
  </SimpleStep>

  <SimpleStep header="T−2 小时">
    开始加注燃料，靶场呈绿灯状态。
  </SimpleStep>

  <SimpleStep header="T−0">
    升空。遥测数据开始传输。
  </SimpleStep>
</SimpleStepper>

## 使用方法 {#use-it}

```mdx
<SimpleStepper>
  <SimpleStep header="Find a launch">
    List launches with room for your payload.
  </SimpleStep>

  <SimpleStep header="Book the slot">
    Create a booking.
  </SimpleStep>
</SimpleStepper>
```

| 属性         | 取值     | 作用                               |
| :--------- | :----- | :------------------------------- |
| `vertical` | `true` | 在 `SimpleStepper` 上：以时间线形式显示所有步骤 |
| `header`   | 文本     | 在 `SimpleStep` 上：步骤的标题           |

<Accordion title="工作原理" icon="fa-wand-magic-sparkles">
  - 文件名为 `SimpleStepperComponent`。它导出 `SimpleStepper` 和 `SimpleStep`，页面可以使用这些标签。
  - [预订发射槽位](/docs/book-a-launch-slot)也使用了它。
</Accordion>
