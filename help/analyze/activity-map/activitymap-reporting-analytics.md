---
description: 介绍设置权限的方法和 Analytics 中的可用维度。
title: Analytics 中的 Activity Map 报告
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 79%

---

# Analytics 中的 Activity Map 报告

介绍设置权限的方法和 Analytics 中的可用维度。

## 设置权限 {#permissions}

要使用户可以报告 Activity Map 维度，管理员需要执行以下操作：

* [将用户添加到Activity Map访问产品配置文件](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* 自定义用户对维度的访问权限。请参阅以下部分。

## AnalyticsActivity Map维度 {#dimensions}

您可以在粒度级别[自定义用户对维度的访问权限](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)。以下是 Analytics 中可用的 Activity Map 维度：

| 维度 | 描述 |
|---|---|
| Activity Map 页面 | 列出单击的链接所在的页面。 |
| Activity Map 区域 | 列出在整个网站中收集的所有链接区域。请注意，如果某个区域在多个页面中出现，则该量度将采用其所有页面的汇总值。 |
| Activity Map 链接 | 列出在整个网站中收集的所有链接。 |
| Activity Map 链接和区域 | 列出在整个网站中收集的所有链接及其区域。 |
| Activity Map XY | 未使用 |

* 只要Analytics实施满足以下条件，这些维度应该可以在Analysis Workspace和Report Builder中使用 [已启用Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* 在Analysis Workspace中，将与活动图相关的维度提取到报表中。
* 要查看特定页面的链接和区域，您只需在 Activity Map 链接和区域中创建一个相应 Activity Map 页面的划分即可。
