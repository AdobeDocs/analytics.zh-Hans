---
title: 变量覆盖
description: 通过变量覆盖，您可以更改单个跟踪的变量值或跟踪链接调用。
translation-type: ht
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de
workflow-type: ht
source-wordcount: '106'
ht-degree: 100%

---


# 变量覆盖

通过变量覆盖，您可以更改一次点击的 Analytics 值，而不影响页面上的现有变量。

## 工作流

1. 创建新的 JavaScript 对象。对象名称可以为您要使用的任何内容。

   ```js
   var y = new Object();
   ```

2. 将有效的 Analytics 属性分配给此对象：

   ```js
   y.eVar1 = "New value";
   y.events = "event2";
   ```

3. 在相应跟踪调用中将对象用作参数：

   ```js
   // Use the override object in a standard page view call
   s.t(y);
   
   // Use the override object in a link tracking call
   s.tl(this,'o','Example override link',y);
   ```

当跟踪调用收到覆盖参数中的某个对象时，该覆盖对象中的所有有效值将覆盖标准 Analytics 对象中的值。在现有 Analytics 对象中已定义的变量将不受影响。
