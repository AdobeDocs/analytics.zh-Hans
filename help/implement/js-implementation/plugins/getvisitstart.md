---
description: 确认是否正在开始新的访问。
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

确认是否正在开始新的访问。

**配置变量**

无

**参数**

c =（字符串）跟踪的 Cookie 名称。

**返回结果**

（整数）访问第一页则返回 1，否则返回 0。

**示例调用**

```
s.eVar50 = s.getVisitStart("s_visit");
```

