---
title: Util.cookieWrite
description: 写入 Cookie 的值。
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/lMhRsrz97N5w8oXBIfwm1FjuVb6epmGeeP3LeO4zXQI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 70%

---

# Util.cookieWrite

Cookie 可以在同一域上的不同页面中存储和检索信息。 使用 `Util.cookieWrite()` 方法将值设置为 Cookie。 您可以使用 [`Util.cookieRead()`](util-cookieread.md) 方法检索使用 `Util.cookieWrite()` 设置的值。

## 使用Adobe Analytics扩展和Web SDK扩展设置Cookie

Adobe Experience Platform数据收集不提供在界面中设置Cookie的功能。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.Util.cookieWrite()

调用 `s.Util.cookieWrite()` 方法可将 Cookie 设置为所需值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

可选的第三个参数可用，该参数用于确定 Cookie 的过期时间。 默认情况下，使用 `s.Util.cookieWrite()` 设置的 Cookie 在浏览器会话结束时过期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 示例

您可以在成功写入 Cookie 时实例化变量。 此变量是一个布尔值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
