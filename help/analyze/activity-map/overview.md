---
description: 通过视觉叠加对链接活动进行排名，以监控网页的受众参与。
title: Activity Map 概述
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 100%

---

# Activity Map 概述

Adobe Analytics Activity Map 是 Adobe Analytics 中的一项功能，它用视觉方式展示用户使用网页和移动设备应用程序的情况。它使营销人员和分析人员可跟踪和分析用户交互，如点击和滚动行为。Activity Map 会生成热图和叠加报告，它们可显示网页上最受欢迎的元素，帮助您优化数字体验。

作为一个概念，Activity Map 由几个重要组件组成：

* **报告包设置**：报告包必须先启用 Activity Map，然后您才能开始使用。请参阅报告包设置中的 [Activity Map 报告](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。
* **实施**：大多数 Activity Map 报告都是现成可用的。但是，某些网站可能需要额外的实施才能充分利用链接跟踪。以下实施变量现在可用：
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：按链接名称筛选点击数据。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：按区域名称筛选点击数据。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)：更改用于填充 Activity Map 区域维度的属性。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md)：自定义 Activity Map 用于填充 Activity Map 链接维度的逻辑。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md)：自定义 Activity Map 用于填充 Activity Map 区域维度的逻辑。
* **叠加**：一种允许您查看网站上叠加点击数据的浏览器扩展。更多信息请参阅 [Activity Map 扩展界面](overlay/overview.md)。此功能不适用于 Web SDK 实施。
* **维度**：除了叠加扩展外，Activity Map 还提供多个可在 Analysis Workspace 中使用的维度。
   * [Activity Map 链接](/help/components/dimensions/activity-map-link.md)：所点击的链接名称。
   * [Activity Map 区域](/help/components/dimensions/activity-map-region.md)：所点击的区域名称。
   * [Activity Map 页面](/help/components/dimensions/activity-map-page.md)：点击链接时的页面名称。
   * [按区域的 Activity Map 链接](/help/components/dimensions/activity-map-link-by-region.md)：Activity Map 链接与 Activity Map 区域的拼接值。

## 功能和好处

* **用户参与的可视化展现**：Activity Map 提供一种用户行为的动态可视化展现形式，使您可准确查看用户在哪里点击。通过这种视觉数据可以更容易地识别模式、趋势和感兴趣的领域。然后，您可以做出关于设计、内容投放和用户流量方面的合理决策。

* **热图**：Activity Map 会生成热图来显示某个网页中点击或交互最多的区域。热图使用颜色编码来表示参与程度，使您能够识别交互热点，优先关注影响力大的区域。此信息对于优化行动号召按钮、链接、表单或任何其他交互元素很有价值。

* **叠加报告**：Activity Map 中的叠加报告可提供某个网页上特定元素的详细点击量度。通过了解各个元素的点击率和参与度，您可以微调您的设计和内容策略，以增强用户体验。此功能不适用于 Web SDK 实施。

* **区段分析**：您可以根据不同的区段分析用户行为，如流量源、人口统计或用户画像。通过对数据分段，您可以发现有关特定用户组的有用洞察，从而实现个性化体验和有针对性的营销策略。

## 实际应用

* **网站优化**：Activity Map 可以确定表现不佳的元素、改进导航、增强整体用户体验，从而帮助您优化网站。通过分析用户交互，您可以制定数据驱动型决策，简化用户流程和表单或调整内容投放，以产生最大影响。

* **转化率优化**：通过将用户参与可视化以及分析点击率，Activity Map 在 CRO 工作中起到至关重要的作用。您可以识别转化障碍并尝试不同的设计变体，以优化转化漏斗、登陆页面和结账过程。

* **A/B 测试**：Activity Map 可以与 A/B 测试结合使用，衡量设计或内容更改产生的影响。通过比较不同网页版本之间的参与量度，您可以确定哪些变体能够提高用户参与、转化率或收入。

