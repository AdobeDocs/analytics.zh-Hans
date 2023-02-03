---
title: pageType
description: 确定当前页面是否为 404 错误。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 56%

---

# pageType

`pageType` 变量是用于指定网站上的错误页面（如 404 错误）的标记。如果此变量包含字符串 `errorPage`，则会填充“页面未找到” [维度](/help/components/dimensions/pages-not-found.md) 和 [量度](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>请勿在非错误页面上设置此变量。

## 使用Web SDK的页面类型

页面类型为 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=zh-Hans) 在XDM字段下 `web.webPageDetails.isErrorPage`. 此XDM字段是一个布尔值；将其设置为 `true` 将其标记为错误页面，或 `false` 如果不是错误页面。 Adobe会自动将布尔值转换为字符串值 `errorPage` 发送到Analytics报表包时。

## 使用Adobe Analytics扩展的页面类型

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.pageType

`s.pageType` 变量是一个字符串，其唯一有效值为 `errorPage`。在网站上的任何错误页面上（如在 404 页面上）将此变量设置为此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 收集错误代码，以便获取有关访客在您的网站上遇到的特定错误的更多信息。
