---
description: 区段管理器提供多种编排区段的方式，如共享、过滤、标记、批准、复制、删除和标记为收藏。
title: 管理区段（区段管理器）
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 8e8f59f747ddacc5462cbc177d199a5e0e91908a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 27%

---

# 区段管理器

区段管理器提供多种编排区段的方式，如共享、过滤、标记、批准、复制、删除和标记为收藏。

Analytics 区段管理器显示了您拥有的所有区段以及共享给您的所有区段。管理员级别的用户可以查看组织内的所有区段。此概述介绍了区段管理器的用户界面和功能。

![区段管理器](assets/segments-manager.png)

## 访问区段管理器

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL 区段]**。

   或

   在现有报表中，选择左侧导航中的区段图标![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)，然后选择&#x200B;**[!UICONTROL 管理]**。

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

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL 区段]**。

1. 在区段管理器中，选择&#x200B;**自定义列**&#x200B;图标![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在区段管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 标题和描述 | 这些值在区段生成器中提供。 要编辑标题和描述，请选择标题链接以打开区段生成器。 |
   | 收藏 | 在每个区段旁边显示星形图标，以使您可以将区段标记为收藏。 有关详细信息，请参阅[将区段标记为收藏](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)。 |
   | 报表包 | 此列指示区段最后保存的报表包。 |
   | 所有者 | 指示区段的所有者。如果是非管理员，则只能看到您拥有的区段或与您分享的区段。 |
   | 标记（在列选择器中未选择，因此列不显示） | 应用到区段的标记，由您或与您共享该区段的人添加。 |
   | 共享对象 | 列出您共享该区段的个人或组（仅管理员）或所有人（仅管理员）。 <p>当您或与您共享区段时，区段名称旁边会显示一个共享图标。</p> |
   | 修改日期 | 显示最后一次修改区段的日期。 |
   | 用在 | 显示区段当前的使用位置以及在每个区域中使用它们的次数。 <p>例如，如果该区段在40个项目和2个警报中使用，则此列的值显示为&#x200B;[!UICONTROL **42个组件**]。</p> <p>选择此列中的值可查看使用区段的细分(例如，[!UICONTROL **项目(40)**]、[!UICONTROL **警报(2)**])。 此外，您还可以查看正在使用区段的项目列表。 例如，查看正在使用它们的项目的列表，选择&#x200B;[!UICONTROL **项目(40)**]&#x200B;链接。</p><p>以下每个区域均显示了该区域中正在使用的区段实例数：</p>  <ul><li>[!UICONTROL **项目**]<p>包含[在区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)中创建并且可用于所有项目的区段。</p></li><li>[!UICONTROL **临时组件**]<p>包含[创建为快速区段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)的区段，并且仅在单个项目中可用。</p></li><li>[!UICONTROL **计划项目**]</li><li>[!UICONTROL **移动记分卡**]</li><li>[!UICONTROL **批注**]</li><li>[!UICONTROL **警报**]</li><li>[!UICONTROL **计算量度**]</li><li>[!UICONTROL **Report Builder**]<p>选择此选项可下载包含以下数据列的CSV文件：</p><ul><li>Report Builder名称</li><li>上次访问</li><li>上次访问的IMS用户ID</li><li>上次访问的用户名</li></ul><p>在查看Report Builder信息时，使用情况信息自2024年9月起可用。</p></li></ul><p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息仅供系统管理员使用。</li><li>默认情况下，[!UICONTROL **Used in**]&#x200B;列不显示。 [配置列](#configure-columns)以显示它。</li><li>如果区段在其定义中包含其他区段，则该区段的任何使用均不会显示在&#x200B;[!UICONTROL **Used in**]&#x200B;列中。 如果区段包含在另一种类型的组件（例如计算量度）的定义中，则使用情况显示在&#x200B;[!UICONTROL **Used in**]&#x200B;列中。</li><li>此信息不包括API或Data Warehouse的使用情况。</li><li>如果此列中没有给定组件的数据，但它具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，则表示该组件可能未保存便已在分析中使用。</li><li>使用情况信息从 2023 年 9 月开始提供。</li></ul><p>您可以将[数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)与此信息一起使用，以帮助您跟踪和更好地了解组织中如何使用组件。</p> |
   | 上次使用时间 | 显示上次在以下任意组件类型中使用区段的日期： <ul><li>警报</li><li>计算量度</li><li>项目</li><li>计划项目</li><li>区段</li></ul> <p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息不包括API、Report Builder或Data Warehouse的使用情况。</li><li>对于某些组件，如果上次在2023年9月之前使用该组件，则此列可能不包含数据。</li><li>此信息仅供系统管理员使用。</li></ul><p>您可以将[数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)与此信息一起使用，以帮助您跟踪和更好地了解组织中如何使用组件。 |

   {style="table-layout:auto"}

## 操作方法视频 {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

这段 [Adobe Analytics 视频](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=zh-Hans)简要概述了区段管理器的使用方法。


