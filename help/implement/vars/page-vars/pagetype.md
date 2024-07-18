---
title: pageType
description: 确定当前页面是否为 404 错误。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

`pageType` 变量是用于指定网站上的错误页面（如 404 错误）的标记。如果此变量包含字符串 `errorPage`，则会填充“页面未找到”[维度](/help/components/dimensions/pages-not-found.md)和[量度](/help/components/metrics/pages-not-found.md)。

>[!IMPORTANT]
>
>请勿在非错误页面上设置此变量。

## 使用 Web SDK 的页面类型

渠道已映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webPageDetails.isErrorPage` — 此XDM字段是布尔值；将其设置为`true`以将其标记为错误页面，如果它不是错误页面，则为`false`。
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.pageType` — 此数据对象字段是字符串；将其设置为`"errorPage"`以将其标记为此类别。

## 使用 Adobe Analytics 扩展的页面类型

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.pageType

`s.pageType` 变量是一个字符串，其唯一有效值为 `errorPage`。在网站上的任何错误页面上（如在 404 页面上）将此变量设置为此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 收集错误代码，以便获取有关访客在您的网站上遇到的特定错误的更多信息。
