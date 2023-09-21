---
description: 区段管理器提供多种编排区段的方式，如共享、过滤、标记、批准、复制、删除和标记为收藏。
title: 管理区段（区段管理器）
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: bd588a06546c59e9a5a61b0260229bafaba150f1
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 35%

---

# 区段管理器

区段管理器提供多种编排区段的方式，如共享、过滤、标记、批准、复制、删除和标记为收藏。

Analytics 区段管理器显示了您拥有的所有区段以及共享给您的所有区段。管理员级别的用户可以查看组织内的所有区段。此概述说明了用户界面和区段管理器的功能。

![区段管理器](assets/segments-manager.png)

## 访问区段管理器

1. 在Adobe Analytics中，选择 **[!UICONTROL 组件]** 选项卡，然后选择 **[!UICONTROL 区段]**.

   或

   在现有报表中，选择区段图标 ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 在左侧导航中，然后选择 **[!UICONTROL 管理]**.

## 区段管理器中的可用操作

在区段管理器中，您可以：

* [过滤区段](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [将区段标记为收藏](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [批准区段](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [标记区段](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [共享区段](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* 将区段导出到CSV文件。

* [复制区段](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [删除区段](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## 配置列

通过配置显示的列，可以配置在区段管理器中为每个区段显示的信息。

要在区段管理器中配置可见列，请执行以下操作：

1. 在Adobe Analytics中，选择 **[!UICONTROL 组件]** 选项卡，然后选择 **[!UICONTROL 区段]**.

1. 在区段管理器中，选择 **自定义列** 图标 ![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在区段管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 标题和描述 | 这些值在区段生成器中提供。 要编辑标题和描述，请选择标题链接以打开区段生成器。 |
   | 收藏 | 在每个区段旁边显示星形图标，以使您可以将区段标记为收藏。 有关更多信息，请参阅 [将区段标记为收藏](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | 报表包 | 此列指示区段最后保存的报表包。 |
   | 所有者 | 指示区段的所有者。如果是非管理员，则只能看到您拥有的区段或与您分享的区段。 |
   | 标记（在列选择器中未选择，因此列不显示） | 应用到区段的标记，由您或与您共享该区段的人添加。 |
   | 共享对象 | 列出您共享该区段的个人或组（仅管理员）或所有人（仅管理员）。 <p>当您或与您共享区段时，区段名称旁边会显示一个共享图标。</p> |
   | 修改日期 | 显示最后一次修改区段的日期。 |
   | 使用位置 | **注意：** 此功能处于版本的有限测试阶段，在您的环境中可能尚未可用。 当该功能正式发布时，将删除此说明。有关Customer Journey Analytics发布过程的信息，请参阅 [Adobe Analytics功能发布](/help/release-notes/releases.md).<p>显示区段当前使用的组件数。 <p>例如，如果该区段在40个项目和2个警报中使用，则此列的值显示为 [!UICONTROL **42个组件**].</p> <p>选择此列中的值可查看使用区段的位置的细分(例如， [!UICONTROL **项目(40)**]， [!UICONTROL **警报(2)**])。</p><p>区段可用于以下任何组件类型中：</p> <ul><li>警报</li><li>项目</li><li>计划项目</li><li>计算量度</li></ul><p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>此信息不包括API、Report Builder或Data Warehouse的使用情况。</p><p>您可以使用 [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。</p><p>此 [!UICONTROL **使用位置**] 默认情况下不显示列。 [配置列](#configure-columns) 以显示。</p> |
   | 上次使用 | **注意：** 此功能处于版本的有限测试阶段，在您的环境中可能尚未可用。 当该功能正式发布时，将删除此说明。有关Customer Journey Analytics发布过程的信息，请参阅 [Adobe Analytics功能发布](/help/release-notes/releases.md).<p>显示上次在以下任意组件类型中使用区段的日期：</p> <ul><li>警报</li><li>计算量度</li><li>项目</li><li>计划项目</li><li>区段</li></ul> <p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>此信息不包括API、Report Builder或Data Warehouse的使用情况。</p><p>您可以使用 [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。 |

   {style="table-layout:auto"}

## 操作方法视频 {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

这段 [Adobe Analytics 视频](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=zh-Hans)简要概述了区段管理器的使用方法。


