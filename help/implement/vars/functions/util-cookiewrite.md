---
title: Util.cookieWrite
description: 写入 Cookie 的值。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieWrite

Cookie 可以在同一域上的不同页面中存储和检索信息。使用 `Util.cookieWrite()` 方法将值设置为 Cookie。您可以使用 [`Util.cookieRead()`](util-cookieread.md) 方法检索使用 `Util.cookieWrite()` 设置的值。

## 在 Adobe Experience Platform Launch 中设置 Cookie

Launch 不提供在界面中设置 Cookie 的功能。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.Util.cookieWrite()

调用 `s.Util.cookieWrite()` 方法可将 Cookie 设置为所需值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

可选的第三个参数可用，该参数用于确定 Cookie 的过期时间。默认情况下，使用 `s.Util.cookieWrite()` 设置的 Cookie 在浏览器会话结束时过期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 示例

您可以在成功写入 Cookie 时实例化变量。此变量是一个布尔值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
