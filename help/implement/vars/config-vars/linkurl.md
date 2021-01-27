---
title: linkURL
description: 覆盖 AppMeasurement 在链接跟踪调用中使用的自动生成的链接 URL。
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 86%

---


# linkURL

每当向 Adobe 发送链接跟踪调用时，数据收集服务器都会自动检测 URL。使用 `linkURL` 变量可覆盖检测到的 URL。

## Adobe Experience Platform Launch 中的“链接 URL”

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkURL

`s.linkURL` 变量是一个字符串，包含点击链接时浏览器的 URL。此变量不会填充报表中可用的任何维度。

```js
s.linkURL = "https://example.com";
```

如果未设置[tl()](../functions/tl-method.md)方法的第三个参数，则使用`linkURL`变量。
