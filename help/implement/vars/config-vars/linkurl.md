---
title: linkURL
description: 覆盖 AppMeasurement 在链接跟踪调用中使用的自动生成的链接 URL。
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 65%

---

# linkURL

每当向 Adobe 发送链接跟踪调用时，数据收集服务器都会自动检测 URL。使用 `linkURL` 变量可覆盖检测到的 URL。

Analysis Workspace中没有报告此变量的维度。 它会填充 `page_event_var1` 中的列 [数据馈送](/help/export/analytics-data-feed/data-feed-overview.md).

## 使用Web SDK的“链接URL”

链接URL已映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `web.webInteraction.URL`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.linkURL` 或 `data.__adobe.analytics.pev1`

## 使用Adobe Analytics扩展的“链接URL”

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkURL

`s.linkURL` 变量是一个字符串，包含点击链接时浏览器的 URL。此变量不会填充报表中可用的任何维度。

```js
s.linkURL = "https://example.com";
```

如果未设置 [tl()](../functions/tl-method.md) 方法的第三个参数，则改用 `linkURL` 变量。
