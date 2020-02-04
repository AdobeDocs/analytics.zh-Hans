---
title: sa
description: 随时在您的实施中更改报表包。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# sa

该方 `sa` 法可让您随时在页面上动态更改报表包。 如果要将数据发送到不同的报表包而无需重新加载页面，则可以使用此方法。

## 在Adobe Experience Platform Launch中使用sa方法

在界面中，没有一种灵活的方法来更改报表包。 配置Adobe Analytics扩展时，可以在“库 [!UICONTROL 管理”] (Library Management)折叠式面板下设置报表包。 但是，您不能使用规则更改或更新报表包。 如果要在设置报表包值后更新这些值，请按照AppMeasurement语法使用自定义代码编辑器。

## s.sa()在AppMeasurement中和启动自定义代码编辑器

调用方 `s.sa()` 法以更改目标报表包。 其唯一参数是包含报表包ID的字符串，或多个以逗号分隔的报表包ID。 报表包ID参数为必填。 请勿在字符串参数中使用空格。

```js
s.sa("examplersid");
```

## 示例

如果用户在您的站点上执行特定操作，则可以更改报表包。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
