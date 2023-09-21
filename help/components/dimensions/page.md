---
title: 页面
description: 页面名称。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 94%

---

# 页面

“页面” [维度](overview.md) 列出您网站上的页面名称。 它是 Adobe Analytics 中最常用的维度之一，因为它可让您深入了解网站上的哪些页面效果最佳。

此维度与[网站区域](site-section.md)维度和[服务器](server.md)维度相关。页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从[页面查看调用 (`t()`)](/help/implement/vars/functions/t-method.md) 中的 [`pageName` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。[链接跟踪调用 (`tl()`)](/help/implement/vars/functions/tl-method.md) 始终剥离此维度，即使存在 `pageName` 查询字符串也是如此。

AppMeasurement 使用 [`pageName`](/help/implement/vars/page-vars/pagename.md) 变量收集此数据。如果未定义 `pageName` 变量，则它回退为使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 变量。

## 维度项目

维度项目包括您的网站上的页面名称。贵组织会确定您要使用的具体维度项目。有些组织直接使用 `document.title`，而另一些组织则制定自定义痕迹导航。无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>在 Reports &amp; Analytics 中，转化指标使用此维度的线性归因。例如，收入在 `purchase` 事件之前的访问中查看的所有页面之间进行拆分。Analysis Workspace 默认使用上一个归因，并且可以选择使用任何归因模型。
