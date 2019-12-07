---
description: 使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。
subtopic: Dashboards
title: 功能板管理器
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 功能板管理器

使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。

>[!IMPORTANT]
>
>使用控制面板管理器的最佳实践是，对于任何单个用户，最多拥有300个仪表板。 另外，请注意，管理器会加载下面所有共享的仪表板，因此，使用共享仪表板时要谨慎。

## 功能板管理器

使用功能板管理器可以复制、共享、存档和计划功能板以进行提交。

Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Dashboards]**.

| 元素 | 描述 |
|--- |--- |
| 共享 | 显示是否共享功能板。 |
| 已设置发布时间 | 让您计划功能板以进行提交。 |
| 查看存档 | 让您查看功能板存档。 此功能在2020年1月将不再可用。 |
| 提交至用户 | 让您共享功能板。 |
| 管理 | 让您编辑、复制和删除功能板。 |

## 管理共享功能板

描述如何使用共享功能板管理选项的步骤。

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Dashboards]**.
1. 在“[!UICONTROL 共享功能板]”下方，找到您要管理的共享功能板（或原有功能板），然后选取下面一个或多个选项：

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> 选项 </th> 
  <th class="chdeschd"> 描述 </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>查看存档</strong></td> 
  <td class="chdesc stentry"> 如果具有存档，则可以查看共享功能板的报表存档。 </td> 
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

> [!NOTE] 展望未来，请考虑使 [用Analysis Workspace项目](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) ，以及下载和计划这些项目的能力。

复制原有功能板时，系统将打开原有功能板以供您编辑，您可添加旧内容或新内容。当您复制原有功能板时，旧内容将保留在原有功能板列表中。

> [!NOTE] 将旧版内容添加到功能板会根据最新的功能板功能创建功能板。 不过，旧缩图报表可能包含以前数据平台的数据。

**迁移版本 14.x 原有功能板**

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Manage Dashboards]**.
1. In the [!UICONTROL Manage] column, under [!UICONTROL Legacy Dashboards], click **[!UICONTROL Copy to New Dashboard]**.

   复制的功能板将在功能板布局编辑器中打开。

   请参阅 [编辑功能板和缩图报表数据](/help/analyze/reports-analytics/dashboard.md).

## 共享功能板

描述管理员如何将功能板共享（或推送）给多个用户的步骤。当您向用户推送功能板时，功能板将在用户的[!UICONTROL 共享功能板]菜单中变为可用。

1. In the [!UICONTROL Dashboard Manager], locate the dashboard, then enable **[!UICONTROL Shared]**.
1. Click **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. On the [!UICONTROL Push Dashboard] page, select the target users or click **[!UICONTROL Check All]**.
1. 单击&#x200B;**[!UICONTROL 保存]**。

如果功能板的共享用户看不到您在功能板中所做的更改，请检查您的功能板管理器，以查看这些用户是否选择了&#x200B;**[!UICONTROL 抄送我]选项。**&#x200B;如果选择了该选项，则他们看不到您所做的更新/更改。为了能够看到所有更改/更新，共享用户需要选择功能板管理器中的&#x200B;**[!UICONTROL 置于菜单]选项。**

## 计划功能板以进行提交

在[!UICONTROL 功能板管理器]中，您可以看到功能板是否已计划进行提交，并且可以编辑计划。功能板提交选项与报表提交选项相同。

1. 打开功能板。
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.

   See [Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) for more information.

## 存档功能板

> [!NOTE] 此功能在2020年1月将不再可用。

描述如何将任何发送的功能板存档为 PDF 文件的步骤。系统会将存档文件保存两年，或直到您存档的报表达到了最大 4 GB 容量限制，以先到者为准。

1. 打开功能板。
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. In the [!UICONTROL Email Report] group, enable **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   您可以在功能板管理器中查看存档的功能板。Alternatively, open a dashboard and click **[!UICONTROL More]** &gt; **[!UICONTROL View Archive]**.
