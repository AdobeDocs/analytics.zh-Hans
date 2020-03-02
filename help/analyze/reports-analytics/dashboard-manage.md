---
description: 使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。
subtopic: Dashboards
title: 功能板管理器
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# 功能板管理器

使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。

>[!IMPORTANT]
>
>使用功能板管理器时的最佳做法是：任何一个用户最多拥有 300 个功能板。另外请注意，管理器会加载下面所有共享的功能板，因此，共享功能板时要谨慎。

## 功能板管理器

使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。

单击 **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| 元素 | 描述 |
|--- |--- |
| 共享 | 显示是否共享功能板。 |
| 已设置发布时间 | 让您计划功能板以进行提交。 |
| 查看存档 | 此功能不再可用。 |
| 提交至用户 | 让您共享功能板。 |
| 管理 | 让您编辑、复制和删除功能板。 |

## 管理共享功能板

描述如何使用共享功能板管理选项的步骤。

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> 选项 </th> 
  <th class="chdeschd"> 描述 </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>查看存档</strong></td> 
  <td class="chdesc stentry"> 此功能不再可用。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>功能板播放器</strong></td> 
  <td class="chdesc stentry"> <p>SiteCatalyst 14 服务器将不再响应功能板播放器数据请求。您可以在标准的“Reports &amp; Analytics”界面中，访问当前显示在功能板播放器内的任何功能板，或者将这些功能板重新创建为“实时功能板”。实时功能板是专为连续显示而设计的，其中包含了一个全屏模式，允许您在电视或其他大屏幕设备上显示功能板。 </p> <p>所需的用户操作：您需要停用功能板播放器。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>抄送我</strong></td> 
  <td class="chdesc stentry"> 使用与原来相同的名称，将一个副本添加到功能板列表中。但是，您无法查看功能板所有者执行的任何更新/更改。复制原有功能板将打开一个空白功能板，您可以在其中添加旧内容。 <p>重要：如果功能板的共享用户看不到您在功能板中所做的更改，请检查您的功能板管理器，以查看这些用户是否选择了<span class="uicontrol">抄送我</span>选项。如果选择了该选项，则他们看不到您所做的更新/更改。为了能够看到所有更改/更新，共享用户需要选择功能板管理器中的<span class="uicontrol">置于菜单</span>选项。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>置于菜单</strong></td> 
  <td class="chdesc stentry"> 允许您查看功能板所有者执行的更改/更新。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>不共享</strong></td> 
  <td class="chdesc stentry"> 从共享功能板的列表中删除此功能板。 </td> 
 </tr> 
</table>

## 迁移原有功能板

现有的旧版功能板将继续运行，而且您仍然可以编辑、下载它们并为其制定计划，但是您不能再新建旧版功能板。强烈建议您将现有旧版功能板升级为较新的功能板格式。

> [!NOTE] 接下来，请考虑使用 [Analysis Workspace 项目](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/)及其将要下载和计划的功能。

复制原有功能板时，系统将打开原有功能板以供您编辑，您可添加旧内容或新内容。当您复制原有功能板时，旧内容将保留在原有功能板列表中。

> [!NOTE] 向功能板添加旧内容时，会基于最新的功能板功能创建一个功能板。不过，旧缩图报表可能包含以前数据平台的数据。

**迁移版本 14.x 原有功能板**

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. 在列的 [!UICONTROL Manage] 下方，单 [!UICONTROL Legacy Dashboards]击 **[!UICONTROL Copy to New Dashboard]**。

   复制的功能板将在功能板布局编辑器中打开。

   请参阅[编辑功能板和缩图报表数据](/help/analyze/reports-analytics/dashboard.md).

## 共享功能板

描述管理员如何将功能板共享（或推送）给多个用户的步骤。When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. 在中， [!UICONTROL Dashboard Manager]找到功能板，然后启用 **[!UICONTROL Shared]**。
1. 单击 **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. 在页面 [!UICONTROL Push Dashboard] 上，选择目标用户或单击 **[!UICONTROL Check All]**。
1. 单击 **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. 如果选择了该选项，则他们看不到您所做的更新/更改。To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## 计划功能板以进行提交

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. 功能板提交选项与报表提交选项相同。

1. 打开功能板。
1. 单击 **[!UICONTROL More]** > **[!UICONTROL Send]**.

   有关更多信息，请参阅[计划和分发](/help/analyze/reports-analytics/scheduling.md)。

## 存档功能板

> [!NOTE] 2020 年 1 月，这项功能将不再可用。

描述如何将任何发送的功能板存档为 PDF 文件的步骤。系统会将存档文件保存两年，或直到您存档的报表达到了最大 4 GB 容量限制，以先到者为准。

1. 打开功能板。
1. 单击 **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. 在组 [!UICONTROL Email Report] 中，启用 **[!UICONTROL Archive]**。
1. Specify delivery options, then click **[!UICONTROL Send]**.

   您可以在功能板管理器中查看存档的功能板。或者，打开功能板并单击 **[!UICONTROL More]** > **[!UICONTROL View Archive]**。
