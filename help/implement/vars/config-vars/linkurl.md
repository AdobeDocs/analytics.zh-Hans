---
title: linkURL
description: 覆盖 AppMeasurement 在链接跟踪调用中使用的自动生成的链接 URL。
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 34%

---

# linkURL

每当向Adobe发送链接跟踪调用时，AppMeasurement都会检测所单击的URL。 此URL可帮助确定链接类型，如下载链接和退出链接。 使用 `linkURL` 变量可覆盖检测到的 URL。

Analysis Workspace中没有报告此变量的维度。 它填充`page_event_var1`数据馈送[中的](/help/export/analytics-data-feed/data-feed-overview.md)列。 如果要跟踪点击链接的URL，Adobe建议使用自定义变量，如[Prop](../page-vars/prop.md)。 使用[Activity Map](/help/analyze/activity-map/overview.md)有助于简化点击链接的数据收集。

## 使用Web SDK的“链接URL”

链接URL已映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webInteraction.URL`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.linkURL`或`data.__adobe.analytics.pev1`

## 使用Adobe Analytics扩展的“链接URL”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkURL

`s.linkURL`变量是一个字符串，包含点击链接的完整URL。 此变量不会填充报表中可用的任何维度。

```js
s.linkURL = "https://example.com";
```

如果未设置 [tl()](../functions/tl-method.md) 方法的第三个参数，则改用 `linkURL` 变量。
