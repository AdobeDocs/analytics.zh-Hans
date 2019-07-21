---
description: 获取 Cookie 的值。
keywords: Analytics 实施
seo-description: 获取 Cookie 的值。
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: 开发人员和实施
uuid: 825a75c6-b804-4bfe-b23 a-907113b8 bfa6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Util.cookieRead

获取 Cookie 的值。

**语法：**

```
s.Util.cookieRead(key)
```

**参数：**

| 参数 | 描述 |
|---|---|
| key | （必需）写入 Cookie 值的键。 |

**返回结果：**

Cookie 值，或者如果找不到 Cookie，则返回空字符串。

**示例：**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

