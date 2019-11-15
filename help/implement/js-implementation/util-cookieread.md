---
description: 获取 Cookie 的值。
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Util.cookieRead

获取 Cookie 的值。

**语法：**

```
s.Util.cookieRead(key)
```

**参数:**

| 参数 | 描述 |
|---|---|
| key | （必需）写入 Cookie 值的键。 |

**返回结果:**

Cookie 值，或者如果找不到 Cookie，则返回空字符串。

**示例：**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

