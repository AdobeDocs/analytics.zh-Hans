---
title: sa
description: 在您的实施中随时更改报表包。
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 94%

---

# sa

`sa()` 方法可让您随时在页面上动态更改报表包。如果要在不重新加载页面的情况下将数据发送到不同的报表包，则可以使用此方法。

## 在Adobe Experience Platform中使用标记的sa方法

界面中没有提供任何灵活的方法来更改报表包。配置 Adobe Analytics 扩展时，可以在[!UICONTROL 库管理]折叠面板下设置报表包。但是，您不能使用规则更改或更新报表包。如果要在设置报表包值后更新这些值，请按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 自定义代码编辑器中的 s.sa()

调用 `s.sa()` 方法以更改目标报表包。其唯一参数是包含报表包 ID 或以逗号分隔的多个报表包 ID 的字符串。报表包 ID 参数为必需参数。请勿在字符串参数中使用空格。

```js
s.sa("examplersid");
```

## 示例

如果用户在您的网站上执行特定操作，则可以更改报表包。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
