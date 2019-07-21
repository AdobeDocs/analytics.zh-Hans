---
description: 自定义事件可让您定义要跟踪的成功类型。
keywords: Analytics实施；自定义事件
seo-description: 自定义事件可让您定义要跟踪的成功类型。
seo-title: 什么是自定义活动？
solution: Analytics
title: 什么是自定义活动？
topic: 开发人员和实施
uuid: e78ba04-9b4c-4566-980c-c24 dd9 d82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# 什么是自定义活动？

自定义事件可让您定义要跟踪的成功类型。

虽然与[!UICONTROL 预定义]事件类似，但[!UICONTROL 自定义]事件可让您定义自己的成功量度。For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. 使用[!UICONTROL 自定义]事件，您可以跟踪注册了您的新闻稿的访客数量。[!UICONTROL 自定义]事件遵循以下标准语法。

```js
s.events="event3"
```

以上代码显示如何将事件分配给&#x200B;_events_ 变量。If you do not modify the event name in the interface, _event3_ would display in the interface.

成功事件默认配置为&#x200B;_计数器_&#x200B;事件。计数器事件可计算成功事件设置的次数。某些成功事件使用需要按自定义金额递增。These events can be set either as _numeric_ events or _currency_ events. 您可以在Admin Console中更改活动类型。
