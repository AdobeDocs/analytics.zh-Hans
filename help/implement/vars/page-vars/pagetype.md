---
title: pageType
description: 确定当前页面是否为 404 错误。
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 77%

---

# pageType

`pageType` 变量是用于指定网站上的错误页面（如 404 错误）的标记。如果此变量包含字符串 `errorPage`，则会填充“页面未找到”维度。

>[!IMPORTANT]
>
>请勿在非错误页面上设置此变量。

## 使用Adobe Analytics扩展的页面类型

Adobe Analytics扩展中没有可使用此变量的专用字段。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.pageType

`s.pageType` 变量是一个字符串，其唯一有效值为 `errorPage`。在网站上的任何错误页面上（如在 404 页面上）将此变量设置为此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 收集错误代码，以便获取有关访客在您的网站上遇到的特定错误的更多信息。
