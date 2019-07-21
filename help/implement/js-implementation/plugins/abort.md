---
description: 可在 doPlugins 中设置中止标记来阻止发送当前的跟踪调用。
keywords: Analytics 实施
seo-description: 可在 doPlugins 中设置中止标记来阻止发送当前的跟踪调用。
seo-title: s.abort 标记
solution: Analytics
title: s.abort 标记
topic: 开发人员和实施
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1 b7 f0 dc
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

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
