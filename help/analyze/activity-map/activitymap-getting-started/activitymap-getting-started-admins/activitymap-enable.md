---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 启用 Activity Map{#enable-activity-map}

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 将您的 AppMeasurement (Javascript) 代码更新至 v1.6（或更高版本）{#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map 模块是 AppMeasurement.js 文件的一部分（位于文件顶部）。AppMeasurement 库在实例化时，将加载 Activity Map 模块。

除非您更新至 AppMeasurement 的这个版本（或更高版本），否则无法收集 Activity Map 数据。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** and [implement it](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/js/overview.html).

   我们已经提供了一些[实现代码样例](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)，以帮助您直观地了解在添加 Activity Map 模块后代码产生的变化。

1. 验证实施:

   1. 点击可点击的元素后，数据就会存储到名为 s_sq 的 Cookie 中。
   1. 可以在用于跟踪调用的查询字符串中看到 Activity Map 数据。例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## 步骤 2. 启用 Activity Map 报表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您需要在报表包级别上启用 Activity Map 报表。

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites >[select report suite]> Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. Activity Map 会收集 Activity Map 报表中的链接数据。For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   该步骤会添加您收集数据所需的所有维度。

1. 大约一小时后，选中 [Activity Map 页面报表](/help/analyze/activity-map/activitymap-reporting-analytics.md)，这样一来，凡是用户单击了其中链接的所有页面，都将显示在报表中。

## 步骤 3. 将用户添加至 Activity Map 访问群组 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 单击 **[!UICONTROL Add Users to Group]**.

   这会把您带入“管理控制台”中的群组管理页面。

1. [将用户添加到此组](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/user-product-management/user-groups/groups.html) 和 **[!UICONTROL Save Group]**。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

>[!NOTE] 如果您希望非管理员用户下载 Activity Map，请新建一个用户组，以提供“工具”和“旧版 ClickMap 安装”的权限。此级别权限与“Activity Map 访问”结合使用，可提供下载和使用该工具的权限。
