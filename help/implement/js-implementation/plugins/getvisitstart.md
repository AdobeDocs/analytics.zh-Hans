---
description: 确认是否正在开始新的访问。
keywords: Analytics 实施
seo-description: 确认是否正在开始新的访问。
seo-title: getVisitStart
solution: Analytics
title: getVisitStart
topic: 开发人员和实施
uuid: 7dd3e51f-2f73-4452-a9 fb-cac513 cd28 eb
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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

