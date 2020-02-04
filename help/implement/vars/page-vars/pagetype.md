---
title: pageType
description: 确定当前页面是否为404错误。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

该 `pageType` 变量是用于指定站点上的错误页面（如404个错误）的标记。 如果此变量包含字符串， `errorPage`则会填充“找不到页面”维。

> [!IMPORTANT] 请勿在非错误页面上设置此变量。

## Adobe Experience Platform Launch中的页面类型

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## s.pageType在AppMeasurement和Launch自定义代码编辑器中

变 `s.pageType` 量是一个字符串，其中值 `errorPage` 是其唯一有效值。 在站点上的任何错误页面上（如404页），将此变量设置为此值。

```js
s.pageType = "errorPage";
```

> [!TIP] 使用eVar收集错误代码，以便获取有关访客在您的网站上遇到哪些特定错误的更多信息。
