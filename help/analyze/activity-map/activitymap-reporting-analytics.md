---
description: 介绍设置权限的方法和 Analytics 中的可用维度。
seo-description: 介绍设置权限的方法和 Analytics 中的可用维度。
seo-title: '[!DNL Activity Map]报告'
solution: Analytics
title: '[!DNL Activity Map]报告'
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] Analytics中的报告

介绍设置权限的方法和 Analytics 中的可用维度。

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [将用户添加到[!DNL Activity Map]访问组](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* 向此群组添加您希望可访问的报表包。Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* 自定义用户对维度的访问权限。请参阅以下部分。

## 分析维 [!DNL Activity Map] 度 {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

您可以在粒度级别[自定义用户对维度的访问权限](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html)。Here are the [!DNL Activity Map] dimensions available in Analytics:

| 维度 | 描述 |
|---|---|
| [!DNL Activity Map] 页面 | 列出单击的链接所在的页面。 |
| [!DNL Activity Map] 区域 | 列出在整个网站中收集的所有链接区域。请注意，如果某个区域在多个页面中出现，则该量度将采用其所有页面的汇总值。 |
| [!DNL Activity Map] 链接 | 列出在整个网站中收集的所有链接。 |
| [!DNL Activity Map] 链接和地区 | 列出在整个网站中收集的所有链接及其区域。 |
| [!DNL Activity Map] XY | 未使用 |

* 这些维度在 Analysis Workspace、Reports &amp; Analytics 和 Report Builder 中应该可用，前提是您已经为 Analytics 实施 [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

