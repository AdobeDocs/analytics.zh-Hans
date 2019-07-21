---
description: 自定义流量变量也称为 prop (s.prop) 或属性变量，是计算每个值发送到 Analytics 的次数的计数器。
keywords: Analytics实施；流量prop；prop；转换；evar；s. prop；自定义转化洞察；流量变量
seo-description: 自定义流量变量也称为 prop (s.prop) 或属性变量，是计算每个值发送到 Analytics 的次数的计数器。
seo-title: prop和eVar概述
solution: Analytics
title: prop和eVar概述
topic: 开发人员和实施
uuid: 522cab2b-1f-4f10-b216-c82 b2231487
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# prop和eVar概述

自定义流量变量也称为 prop (s.prop) 或属性变量，是计算每个值发送到 Analytics 的次数的计数器。

确定哪些变量应分配到哪里时，非常重要的一点是理解 Prop 与 eVar 功能之间的区别。了解这些区别可帮助您的组织确定最适用的变量类型。有关详细信息，请参阅 [比较 Prop 和 eVar](../../../implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md#concept_6E55483C1EC24566B5D3B2736E766EBC).

Prop 还可让您将自定义数据与特定流量相关事件关联。这些变量嵌入在网站每个页面上的 [!DNL Analytics] 代码中。通过 [!UICONTROL s.prop] 变量，[!DNL Analytics] 可让您创建组织、行业和业务目标特有的自定义报表。

例如，如果您是汽车制造商，可能会有兴趣查看“Most Popular Car Model”以补充“页面”报表。为此，可分配一个表示汽车型号的流量属性。然后实施代码以在相应的页面上传递汽车型号。

>[!NOTE]
>
>[!DNL Analytics] 最多支持75 [!UICONTROL s. prop] 变量。

Prop 用于路径报表或关联报表中。例如，[!UICONTROL 属性]变量可用来显示内容类型、子区域或模板名称。生成的[!UICONTROL 自定义流量]报表显示最常查看的内容类型、子区域或模板。

根据您从网站中捕获的信息，通过自定义流量变量可回答各种业务问题。下表列出了常见的目标和目的：

* 了解用户在网站中的导航情况
* 了解内部用户的搜索行为
* 按导航或类别划分流量区段
* 按人口统计划分访客行为区段

eVar（或[!UICONTROL 自定义转化分析]变量）用于确定特定属性或操作对于网站上的成功事件有多大贡献。例如，对于媒体网站，可以使用 eVar 确定内部促销是否能有效地引导访客进行注册。在访客点击内部促销时，可以使用 eVar 存储该促销的唯一标识符。在同一访客完成注册并触发自定义成功事件时，原始的唯一标识符为注册事件接收信用。

在转化网站中，可以使用 eVar 跟踪已登录访客与未登录访客在完成购买方面的对比情况。访客登录时，eVar 会被设置为“已登录”。在访客到达结账页面时，将结账事件与“已登录”值关联。当访客完成购买到达“感谢”页面时，将产品和购买量与“已登录”值关联。生成的[!UICONTROL 自定义 eVar] 报表显示“已登录”及“未登录”访客的结账和订单总数。

有关更多信息，请参阅“Analytics 帮助和参考”指南中的[流量变量](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html)。

有关如何在动态标签管理中设置属性的信息，请参阅[创建 Web 属性](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)。
