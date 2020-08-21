---
title: pageType
description: 确定当前页面是否为 404 错误。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '135'
ht-degree: 100%

---


# pageType

`pageType` 变量是用于指定网站上的错误页面（如 404 错误）的标记。如果此变量包含字符串 `errorPage`，则会填充“页面未找到”维度。

>[!IMPORTANT]
>
>请勿在非错误页面上设置此变量。

## Adobe Experience Platform Launch 中的页面类型

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.pageType

`s.pageType` 变量是一个字符串，其唯一有效值为 `errorPage`。在网站上的任何错误页面上（如在 404 页面上）将此变量设置为此值。

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>使用 eVar 收集错误代码，以便获取有关访客在您的网站上遇到的特定错误的更多信息。
