---
title: Util.cookieWrite
description: 写入cookie的值。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieWrite

Cookies可以在同一域上跨页面存储和检索信息。 使用 `Util.cookieWrite` 该方法将值设置为cookie。 您可以使用该 `Util.cookieRead` 方法检索使用设置的值 `Util.cookieWrite`。

## 在Adobe Experience Platform Launch中设置Cookie

Launch不提供在界面中设置Cookie的功能。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.Util.cookieWrite()和启动自定义代码编辑器

调用 `s.Util.cookieWrite()` 方法，将cookie设置为所需值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

可选的第三个参数可用，用于确定Cookie的过期时间。 默认情况下， `s.Util.cookieWrite()` 使用设置的Cookie在浏览器会话结束时过期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 示例

在成功编写cookie后，您可以实例化变量。 此变量是布尔值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
