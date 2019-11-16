---
description: 解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。
solution: Analytics
title: 启用 Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 启用 Activity Map{#enable-activity-map}

解释为了启用 Activity Map 链接收集和用户下载，Analytics 管理员需要完成的步骤。

## 步骤 1. 将您的 AppMeasurement (Javascript) 代码更新至 v1.6（或更高版本）{#section_5D1586289DF2489289B1B6C1C80C300D}

Activity Map 模块是 AppMeasurement.js 文件的一部分（位于文件顶部）。AppMeasurement 库在实例化时，将加载 Activity Map 模块。

除非您更新至 AppMeasurement 的这个版本（或更高版本），否则无法收集 Activity Map 数据。

1. 通过转至 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 代码管理器]**&#x200B;下载最新的 AppMeasurement 代码 (AppMeasurement_Javascript-1.6.zip) 并[实现该代码](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html)。

   我们已经提供了一些[实现代码样例](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md)，以帮助您直观地了解在添加 Activity Map 模块后代码产生的变化。

1. 验证实施:

   1. 点击可点击的元素后，数据就会存储到名为 s_sq 的 Cookie 中。
   1. 可以在用于跟踪调用的查询字符串中看到 Activity Map 数据。例如：

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. 按照 **[!UICONTROL Activity Map 链接（按区域）]**&#x200B;划分此报表时，可以查看该页面的链接/区域：![](assets/am_breakdown.png){width="400px"}

## 步骤 2. 启用 Activity Map 报表 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

首先，您需要在报表包级别上启用 Activity Map 报表。

1. 登录 Adobe Analytics，然后导航至 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员 &gt; 报表包 &gt;[选择报表包]&gt; 编辑设置 &gt; Activity Map]** &gt; **[!UICONTROL Activity Map 报告]**。
1. Activity Map 会收集 Activity Map 报表中的链接数据。为了激活，您必须首先通过单击&#x200B;**[!UICONTROL 启用 Activity Map 报表]**&#x200B;来激活变量。

   该步骤会添加您收集数据所需的所有维度。

1. 大约一小时后，选中 [Activity Map 页面报表](/help/analyze/activity-map/activitymap-reporting-analytics.md)，这样一来，凡是用户单击了其中链接的所有页面，都将显示在报表中。

## 步骤 3. 将用户添加至 Activity Map 访问群组 {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. 单击&#x200B;**[!UICONTROL 将用户添加至组]**。

   这会把您带入“管理控制台”中的群组管理页面。

1. [将用户添加至组](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)并&#x200B;**[!UICONTROL 保存群组]**。

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

> [!NOTE] 如果您希望非管理员用户下载 Activity Map，请新建一个用户组，以提供“工具”和“旧版 ClickMap 安装”的权限。此级别权限与“Activity Map 访问”结合使用，可提供下载和使用该工具的权限。
