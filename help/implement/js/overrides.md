---
title: 变量覆盖
description: 通过变量覆盖，您可以更改单个跟踪的变量值或跟踪链接调用。
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# 变量覆盖

变量覆盖允许您更改一次点击的分析值，而不会影响页面上的现有变量。

## 工作流

1. 创建新的JavaScript对象。 对象名称可以是您需要的任何内容。

   ```js
   var y = new Object();
   ```

2. 为此对象分配有效的Analytics属性：

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. 将对象用作相应跟踪调用中的参数：

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

当跟踪调用收到覆盖参数中的对象时，覆盖对象中的所有有效值将覆盖标准Analytics对象中的值。 现有Analytics对象中已定义的变量不受影响。
