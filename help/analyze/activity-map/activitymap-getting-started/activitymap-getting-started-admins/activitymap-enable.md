---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 启用 Activity Map{#enable-activity-map}

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 将您的 AppMeasurement (Javascript) 代码更新至 v1.6（或更高版本）{#section_5D1586289DF2489289B1B6C1C80C300D}

活动图模块是AppMeasurement.js文件（位于文件顶部）的一部分。 实例化后，AppMeasurement库将加载活动映射模块。

除非您更新至此版本（或更高版本）的AppMeasurement，否则无法收集活动图数据。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/zh_CN/sc/implement/js_implementation.html).

   我们包含了一些 [示例实施代码](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) ，以帮助您通过包括活动图模块来可视化对代码所做的更改。

1. 验证实施:

   1. 单击可单击的元素时，数据将存储在名为s_sq的cookie中。
   1. 活动映射数据可在跟踪调用的查询字符串中查看。 例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 步骤 2. 启用 Activity Map 报表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您需要在报表包级别上启用 Activity Map 报表。

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites >[select report suite]> Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map 会收集 Activity Map 报表中的链接数据。For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   此步骤将添加您收集数据所需的所有Analytics维度。

1. 大约一小时后，请查看 [活动图页面报告](/help/analyze/activity-map/activitymap-reporting-analytics.md)，该报告显示用户单击链接的所有页面。

## 步骤 3. 将用户添加至 Activity Map 访问群组 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 单击 **[!UICONTROL Add Users to Group]**.

   这会把您带入“管理控制台”中的群组管理页面。

1. [将用户添加到此组](https://marketing.adobe.com/resources/help/zh_CN/reference/groups.html) 和 **[!UICONTROL Save Group]**。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE] 如果您希望非管理员用户下载 Activity Map，请新建一个用户组，以提供“工具”和“旧版 ClickMap 安装”的权限。此级别权限与“Activity Map 访问”结合使用，可提供下载和使用该工具的权限。
