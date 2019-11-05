---
description: 创建一个项目并将组件（维度、量度、区段、日期范围）添加到自由格式面板。
keywords: Analysis Workspace
seo-description: 创建一个项目并将组件（维度、量度、区段、日期范围）添加到自由格式面板。
seo-title: 创建 Workspace 项目
solution: Analytics
title: 创建 Workspace 项目
topic: Reports and Analytics
uuid: c1def77a-a76e-4699-9feb-1ede5b70b7ba
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 创建 Workspace 项目

创建一个项目并将组件（维度、量度、区段、日期范围）添加到自由格式面板。

在本篇文章中，您可以熟悉 Analysis Workspace 的界面元素，并了解如何创建项目。有关特定用例，请参 [阅Analysis Workspace的用例](/help/analyze/analysis-workspace/freeform-analysis-examples-use-cases.md)。

## 创建项目

1. 指定创建和管理项目的用户权限。

   创建或组织 Analysis Workspace 项目之前，管理员必须要将您添加到具有&#x200B;**[!UICONTROL 在 Analysis Workspace 中创建/组织项目]**&#x200B;权限的组，或者添加到&#x200B;**全部报表访问]用户组。[!UICONTROL **( **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; [Groups](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)).

1. In the [!DNL Experience Cloud], click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   或者，输入正斜杠 (/) 以打开报表搜索栏，然后键入“分析工作区 *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Click **[!UICONTROL Create New Project]**.

   您可以选择从以下项创建项目：

* 空白项目（默认）。有关说明，请参阅下文。
* 标准模板。这些模板由 Adobe 创建并且即装即用。有关说明，请参阅[模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。
* 自定义模板。这些模板由具有管理员权限的用户创建。有关说明，请参阅[模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。

   ![](assets/start_modal.png)

1. To create a project from a blank project, click **[!UICONTROL Blank Project]**.

   * Then click **[!UICONTROL Create]**, or
   * Simply click **[!UICONTROL Enter]**.
   屏幕上会显示空白项目，其中包括一个自由格式面板和一个数据表可视化信息。

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >有时，在加载项目（或切换到报表包）时，“不兼容的报表包”消息会显示，其中并非项目中包含的所有组件（度量／维度）都包含在报表包中。 您可以看到不兼容的组件列表，这样便可以了解为什么会收到该消息。

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > 组件</a> </td> 
   <td colname="col2"> <p>可拖入项目中的维度、量度、区段和日期范围。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 可视化</a> </td> 
   <td colname="col2"> <p>这些项目可拖至界面上的面板或项目区域中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table.md"  > 自由格式面板 </a> </td> 
   <td colname="col2"> <p>用于在 Analysis Workspace 中进行交互的画布或工作区。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 保存项目。Name the project, provide a description (optional, but useful) and tag the project (optional), then click **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. 现在，您可以右键单击并复制可视化或面板，然后将复制的可视化或面板粘贴（“插入”）到同一项目的其他位置或其他项目中。

   您可以利用此项功能来创建一些能够复制到其他项目中的“构建基块”（预定义的可视化/面板），从而更加快速地运用特定于您公司的数据。

   >[!NOTE]
   >
   >复制／另存为后，内部链接现在相对于它们所在的项目，而不是它们从中复制的原始项目。

## 添加组件和可视化 {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. 通过拖动和拖到项 *`components`* 目来 *`visualizations`* 构建项目。

   **组件**

   “组件”工具栏显示了您最常使用的一些可搜索的维度、量度、区段以及日期范围。

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 维度（橙色） </td> 
   <td colname="col2"> <p>应用于项目级别。 </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#、eVar# 和 event# 均被附加到维度名称，您可以对这些数字编号进行搜索。示例：“Internal Campaign”在左边栏中显示为“Internal Campaign (event1)”。 </p> <p> 请注意，表中不显示 prop、eVar 和 event 编号（为了使标题保持简短）。 </p> <p>某些现有的维度在被拖到自由格式表中或在左边栏中被人查看时具有默认的排序顺序。例如，如果将“小时”放入表中或在左边栏中查看它时，它将按照从 12AM 至 11PM 的顺序进行排序。您仍然可以选择按照任何量度列进行排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度（绿色） </td> 
   <td colname="col2"> <p>应用于项目级别。 </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> 发生次数</span> ，是数据表的默认度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 区段（蓝色） </td> 
   <td colname="col2"> <p>只能在面板级别进行拖动，不过，您可以在数据表中创建内联区段。 </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>有关详 <a href="/help/analyze/analysis-workspace/freeform-analysis-examples-use-cases.md"  > 细信息，请参阅Analysis Workspace的使用案例</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日期范围和粒度（紫色） </td> 
   <td colname="col2"> <p>只能在面板级别进行拖动。配置日期范围时，您可以通过“日历”创建一个项目。 </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

[!UICONTROL 可视化]面板提供标准的 Analytics 图形、图表、圆环图、数据表、[同类群组](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)表、维恩图等等。您可以将多个可视化信息拖放到项目中。

![步骤结果](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. 步骤

## 使用右键单击菜单自定义您的数据 {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

右键单击菜单允许您执行以下操作，具体操作取决于您在表格中右键单击的单元格。

![步骤结果](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 操作 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 添加时间段列</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 比较时间段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>复制到剪贴板 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>删除选定项 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > 从选定范围中创建警报</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > 划分</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">维度 </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">量度 </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">区段 </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">时间 </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 可视化</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > 下载为 CSV 格式</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/analysis-workspace-features.md"  > 趋势选择</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > 从选定范围中创建区段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"  > 在区段比较中运行</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 只显示选定的行 </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 显示所有行 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

有关复制和选择行的信息，请参阅[在 Analysis Workspace 中可使用键盘、鼠标交互等行为](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。
