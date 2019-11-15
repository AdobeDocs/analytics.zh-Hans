---
description: 可在 doPlugins 中设置中止标记来阻止发送当前的跟踪调用。
keywords: Analytics Implementation
solution: Analytics
title: s.abort 标记
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.abort 标记

可在 doPlugins 中设置中止标记来阻止发送当前的跟踪调用。

中止标记已通过每个跟踪呼叫进行重置，因此，如果还需要中止后续跟踪呼叫，则需要在 doPlugins 内重新设置标记。

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

这可让您将用于确认您不希望跟踪的活动的逻辑集中在一起，如一些自定义链接或显示广告中的外部链接。
