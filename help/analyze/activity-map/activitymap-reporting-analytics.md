---
description: 介绍设置权限的方法和 Analytics 中的可用维度。
title: Analytics 中的 Activity Map 报告
topic: Activity map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Analytics 中的 Activity Map 报告

介绍设置权限的方法和 Analytics 中的可用维度。

## 设置权限 {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

要使用户可以报告 Activity Map 维度，管理员需要执行以下操作：

* [将用户添加至 Activity Map 访问群组](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* 向此群组添加您希望可访问的报表包。导航到 **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**。
* 自定义用户对维度的访问权限。请参阅以下部分。

## Analytics Activity Map 维度 {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

您可以在粒度级别[自定义用户对维度的访问权限](https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)。以下是 Analytics 中可用的 Activity Map 维度：

| 维度 | 描述 |
|---|---|
| Activity Map 页面 | 列出单击的链接所在的页面。 |
| Activity Map 区域 | 列出在整个网站中收集的所有链接区域。请注意，如果某个区域在多个页面中出现，则该量度将采用其所有页面的汇总值。 |
| Activity Map 链接 | 列出在整个网站中收集的所有链接。 |
| Activity Map 链接和区域 | 列出在整个网站中收集的所有链接及其区域。 |
| Activity Map XY | 未使用 |

* 这些维度在 Analysis Workspace、Reports &amp; Analytics 和 Report Builder 中应该可用，前提是您已经为 Analytics 实施[启用了 Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* 在Reports &amp; Analytics中，导航到 **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]**。

* 要查看特定页面的链接和区域，您只需在 Activity Map 链接和区域中创建一个相应 Activity Map 页面的划分即可。

