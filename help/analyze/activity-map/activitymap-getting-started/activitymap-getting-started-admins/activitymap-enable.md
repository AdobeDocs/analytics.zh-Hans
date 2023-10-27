---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
title: 启用 Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: d4caf0ddc5cf5402bfef94a64db1c00e1c725658
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 74%

---

# 启用 Activity Map{#enable-activity-map}

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 更新您的实施代码 {#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map模块是AppMeasurement.js和Web SDK（版本2.15.0或更高版本）的一部分。
AppMeasurement库或Web SDK将在实例化时加载Activity Map模块。

>[!NOTE]
>
>除非您更新到，否则无法收集Activity Map数据 **AppMeasurement** **版本1.6** 或更高或 **Web SDK** **版本2.15.0** 或更高。


1. 根据您使用的是AppMeasurement还是Web SDK，下载最新的Javascript库。

   - **AppMeasurement** 代码(AppMeasurement_Javascript-1.6.zip)，方法是转到  **[!UICONTROL 分析]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 代码管理器]** 和 [实施](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=zh-Hans).

     我们已经提供了一些[实现代码样例](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)，以帮助您直观地了解在添加 Activity Map 模块后代码产生的变化。

   - **Web SDK** 代码(alloy.js)。 请参阅 [安装SDK — 选项2：安装预生成的独立版本](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans#option-2%3A-installing-the-prebuilt-standalone-version) 以了解更多信息。 确保使用版本2.15或更高版本。

     请参阅 [跟踪链接](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) 有关如何实施链接跟踪以及如何通过捕获 `region` 点击的HTML元素的ID。

     >[!NOTE]
     >
     >当客户从一个页面导航到下一个页面时，用 Web SDK 启用链接跟踪当前将发送链接事件。这与 AppMeasurement 的工作方式不同，并且可能会导致将额外的可计费点击数发送到 Adobe。


1. 验证实施:

   1. 点击可点击的元素后，数据就会存储到名为 s_sq 的 Cookie 中。
   1. 可以在用于跟踪调用的查询字符串中看到 Activity Map 数据。例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. 按照 **[!UICONTROL Activity Map 链接（按区域）]**&#x200B;划分此报表时，可以查看该页面的链接/区域：  ![](assets/am_breakdown.png){width="400px"}

## 步骤 2. 启用 Activity Map 报表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您需要在报表包级别上启用 Activity Map 报表。

1. 登录 Adobe Analytics，然后导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > 选择报表包 > **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 报告]**。
1. Activity Map 会收集 Activity Map 报表中的链接数据。为了激活，您必须首先通过单击&#x200B;**[!UICONTROL 启用 Activity Map 报表]**&#x200B;来激活变量。

   该步骤会添加您收集数据所需的所有维度。

1. 大约一小时后，选中 [Activity Map 页面报表](/help/analyze/activity-map/activitymap-reporting-analytics.md)，这样一来，凡是用户单击了其中链接的所有页面，都将显示在报表中。

## 步骤 3. 将用户添加至 Activity Map 访问群组 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 单击&#x200B;**[!UICONTROL 将用户添加至组]**。

   这会把您带入“管理控制台”中的群组管理页面。

1. [将用户添加至组](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=zh-Hans)并&#x200B;**[!UICONTROL 保存群组]**。

1. 这可以允许您的管理员用户从 **[!UICONTROL Adobe Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL Activity Map]** 下载 Activity Map。

>[!NOTE]
>
>如果您希望非管理员用户下载 Activity Map，请新建一个用户组，以提供“工具”和“旧版 ClickMap 安装”的权限。此级别权限与“Activity Map 访问”结合使用，可提供下载和使用该工具的权限。
