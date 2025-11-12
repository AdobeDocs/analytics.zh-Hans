---
description: 了解如何使用区段管理器管理区段（例如共享、筛选、标记、批准、复制、删除区段）以及将区段标记为收藏。
title: 管理区段
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 63%

---

# 管理区段


您可以在[!UICONTROL 区段]中央管理界面中[分享](t-seg-share.md)、[分段](t-seg-filter.md)、[标记](seg-tag.md)、[批准](seg-approve.md)、重命名、[复制](seg-copy.md)、删除、导出区段以及将区段标记为[收藏](t-seg-favorite.md)。要管理区段：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 区段]**。


>[!NOTE]
>
>您在特定Workspace项目中所创建的快速区段不会显示在[!UICONTROL 区段]管理器中，除非您已将区段设置为对所有项目都可用。
>

## 区段管理器

区段管理器具有以下界面元素：

![区段界面](assets/segments-manager.png)

### 区段列表

区段列表➊显示您拥有的所有区段、已确定范围到您的所有项目的区段以及与您共享的区段。 该列表具有以下各列：

| 列 | 描述 |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择以将一个区段加入收藏 ![Star](/help/assets/icons/Star.svg) 或取消收藏 ![StarOutline](/help/assets/icons/StarOutline.svg)。参阅[将区段标记为收藏](t-seg-favorite.md) |
| **[!UICONTROL 标题和描述]** | 要编辑区段，请选择标题链接，这会打开[区段生成器](seg-build.md)。 ![分享](/help/assets/icons/ShareAlt.svg)表示了这是共享区段。 |
| **[!UICONTROL 报表包]** | 此区段应用于的报表包。 |
| **[!UICONTROL 所有者]** | 区段的所有者。作为用户，您只能看到您拥有的区段或与您共享的注释。 |
| **[!UICONTROL 标记]** | 此区段的标记。 |
| **[!UICONTROL 共享对象]** | 您与多少个人或群组共享此区段。选择以打开&#x200B;**[!UICONTROL 分享组件]**&#x200B;对话框。有关更多信息，请参阅[共享区段](t-seg-share.md)。 |
| **[!UICONTROL 已发布]** | [区段是否已发布](seg-publish.md)到Experience Cloud。 |
| **[!UICONTROL 修改日期]** | 上次更改区段的日期和时间。 |

使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 指定您想要显示的列。

### 操作栏

您可以使用操作栏➋对区段执行操作。 该操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[区段生成器](seg-build.md)添加另一个区段。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 如果在列表中未选择任何区段，使用此搜索字段搜索区段。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标记]** | 标记选定的区段。在&#x200B;**[!UICONTROL 标记区段]**&#x200B;对话框中，选择或取消选择所选区段的标记。选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选区段的标记。有关更多信息，请参阅[标记区段](seg-tag.md)。 |
| ![共享](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共享]** | 共享选定的区段。在&#x200B;**[!UICONTROL 分享区段]**&#x200B;对话框中，您可以 ![搜索](/help/assets/icons/Search.svg) *搜索个人或群组*，或者您可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或者&#x200B;**[!UICONTROL 群组]**。选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选区段的共享详细信息。有关更多信息，请参阅[共享区段](t-seg-share.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除选定的区段。系统将提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 重命名]** | 重命名单个选定的区段。选中后，您可以通过内联的方式重命名该区段。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 批准]** | 批准选定的区段。有关更多信息，请参阅[批准区段](seg-approve.md)。 |
| ![复制](/help/assets/icons/Copy.svg)  **[!UICONTROL 复制]** | 复制选定的区段。使用相同的名称和后缀创建新的区段 `(Copy)`。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出为 CSV]** | 将区段导出至 `Segments List.csv` 文件。 |

### 活动过滤器栏

筛选器栏➌显示从筛选器面板应用于区段列表（如果有）的活动区段。 您可以使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 快速移除过滤器。如果指定了多个筛选器，则可以使用&#x200B;**[!UICONTROL 删除所有]**&#x200B;来删除所有筛选器。

### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板➍来筛选区段列表。 过滤器面板显示过滤器的类型和遵循特定过滤器的区段数。 选择![筛选器](/help/assets/icons/Filter.svg)切换筛选器面板的显示。

请参阅[过滤区段列表](t-seg-filter.md)，以了解更多信息。


<!--

The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment manager

In the Segment manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment manager by configuring the columns that are displayed.

To configure the visible columns in the Segment manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=zh-Hans) gives a short overview of how to use the Segment manager.

-->