---
description: 将值写入到 Cookie。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

将值写入到 Cookie。

**语法：**

```
s.Util.cookieWrite(key, value [,expire])
```

**参数:**

| 参数 | 描述 |
|---|---|
| key | （必需）写入 Cookie 值的键。 |
| value | （可选）要写入 Cookie 的值。 |
| expire | （可选）包含 Cookie 过期日期的日期对象。默认使用会话 Cookie。 |

**返回结果:**

**示例：**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

