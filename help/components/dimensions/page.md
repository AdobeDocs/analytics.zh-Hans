---
title: 页面
description: 页面名称。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 71%

---


# 页面

“页面”维度列出网站上的页面名称。它是 Adobe Analytics 中最常用的维度之一，因为它可让您深入了解网站上的哪些页面效果最佳。

此维度与[网站区域](site-section.md)维度和[服务器](server.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维从页面查询调 [`pageName` 用(](/help/implement/validate/query-parameters.md) ) [中的字符串检`t()`索视图](/help/implement/vars/functions/t-method.md)。 [链接跟踪调用`tl()`(](/help/implement/vars/functions/tl-method.md) )始终会删除此维，即使存 `pageName` 在查询字符串。

AppMeasurement 使用 [`pageName`](/help/implement/vars/page-vars/pagename.md) 变量收集此数据。If the `pageName` variable is not defined, it falls back to using the [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variable.

## Dimension项

Dimension项包括站点上的页面名称。 您的组织确定要使用哪些特定维项目。 有些组织直接使用 `document.title`，而另一些组织则制定自定义痕迹导航。无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>在 Reports &amp; Analytics 中，转化量度使用此维度的线性归因。例如，收入在 `purchase` 事件之前的访问中查看的所有页面之间进行拆分。Analysis Workspace 默认使用上一个归因，并且可以选择使用任何归因模型。
