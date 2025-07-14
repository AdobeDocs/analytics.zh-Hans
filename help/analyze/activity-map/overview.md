---
description: 使用可视化叠加图对链接活动进行排名，以监控网页的受众参与。
title: Activity Map 概述
feature: Activity Map
role: User, Admin
exl-id: 30a800f7-e2c8-443e-b5d4-36834ef0ba20
source-git-commit: dee8f0a13a159f4c7902d2ccddd8848c4016b471
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# Activity Map 概述

Adobe Analytics Activity Map 是 Adobe Analytics 中的一项功能，它用视觉方式展示用户使用网页和移动设备应用程序的情况。它允许营销人员和分析人员跟踪和分析用户交互，如点击次数和滚动行为。 Activity Map生成热图和叠加报表，这些报表显示网页上最受欢迎的元素，可帮助您优化数字体验。

本文档的这一部分重点介绍Activity Map叠加。 但是，使用Activity Map还有其他重要部分：

* **报表包设置**：报表包必须启用Activity Map。 请参阅报表包设置中的[Activity Map报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)。
* **实施**：大多数Activity Map报表都是现成可用的。 但是，某些网站可能需要额外的实施才能充分利用链接跟踪。 以下实施变量可供使用：
   * [`ActivityMap.linkExclusions`](/help/implement/vars/config-vars/activitymap-linkexclusions.md)：按链接名称筛选点击数据。
   * [`ActivityMap.regionExclusions`](/help/implement/vars/config-vars/activitymap-regionexclusions.md)：按区域名称筛选点击数据。
   * [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)：更改填充Activity Map Region维度的属性。
   * [`ActivityMap.link`](/help/implement/vars/functions/activitymap-link.md)：自定义Activity Map用于填充Activity Map链接维度的逻辑。
   * [`ActivityMap.region`](/help/implement/vars/functions/activitymap-region.md)：自定义Activity Map用于填充Activity Map区域维度的逻辑。
* **维度**：除了叠加扩展之外，Activity Map还提供了多个可在Analysis Workspace中使用的维度。
   * [Activity Map链接](/help/components/dimensions/activity-map-link.md)：已单击的链接名称。
   * [Activity Map地区](/help/components/dimensions/activity-map-region.md)：被点击的地区名称。
   * [Activity Map页面](/help/components/dimensions/activity-map-page.md)：链接被单击时的页面名称。
   * [按地区](/help/components/dimensions/activity-map-link-by-region.md)列出的Activity Map链接： Activity Map链接与Activity Map地区的拼接值。

## 功能和优点

* **用户参与可视化**： Activity Map提供了用户行为的动态可视化表示形式，使您可准确查看用户点击的位置。 这种视觉数据更容易识别模式、趋势和感兴趣的领域。 然后，您可以针对设计、内容放置和用户流量做出明智的决策。

* **热图**： Activity Map生成显示网页中点击次数或交互次数最多的区域的热图。 热图使用颜色编码来表示参与程度，使您能够识别热点并优先关注高影响力的区域。 此信息对于优化call-to-action按钮、链接、表单或任何其他交互式元素非常有用。

* **叠加报表**： Activity Map中的叠加报表为网页上的特定元素提供了详细的点击量度。 通过了解各个元素的点进率和参与级别，您可以优化设计和内容策略以提升用户体验。

* **区段分析**：您可以根据不同的区段分析用户行为，如流量源、人口统计或角色。 通过对数据进行分段，您可以揭示针对特定用户组的宝贵见解，从而实现个性化体验和有针对性的营销策略。

## 实际应用

* **网站优化**： Activity Map通过识别性能不佳的元素、改进导航并增强整体用户体验，帮助您优化网站。 通过分析用户交互，您可以制定数据驱动型决策，以简化用户流、简化表单或调整内容放置以获得最大影响。

* **转化率优化**：通过可视化用户参与度和分析点进率，Activity Map在CRO工作中将发挥关键作用。 您可以识别转化的障碍，并使用不同的设计变体进行试验，以优化转化漏斗、登陆页面和结账流程。

* **A/B测试**：可以将Activity Map与A/B测试结合使用，以衡量设计或内容更改的影响。 通过比较不同网页版本之间的参与量度，您可以确定哪些变化会导致更高的用户参与度、转化率或收入。

