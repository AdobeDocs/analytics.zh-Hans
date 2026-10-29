---
description: 了解管理员如何使用报表包或数据字典向组件添加描述。
title: 添加组件描述
feature: Components
role: Admin
exl-id: db36ee4a-66e2-45d1-8b7a-49570b5fce93
TQID: https://experienceleague.adobe.com/8z9vnSfrxEb1nkOlTTlHrp3BdElFJmTjbsSLBGbE7Gs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b3d9fb81837398b349496ec261dc1d0ba3df3645
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 20%
---
# 添加组件描述

描述帮助用户了解如何在 Analysis Workspace 中构建项目时或在查看报表时最佳地使用各个组件。

Analytics管理员可以在报表包中或直接使用Analysis Workspace中的数据字典为组件（维度、量度、区段和日期范围）添加描述。

## 报告包

您可以向报表包中的组件添加描述。

1. 选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 报表包]**。
1. 在报表包管理器中选择要为其提供组件说明的报表包。
1. 选择&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化变量]**。
1. 选择![添加](/help/assets/icons/Add.svg)以显示转化变量的详细信息。
1. 选中&#x200B;**[!UICONTROL 描述]**&#x200B;的复选框并添加描述。
1. 对要添加说明的任何其他变量重复步骤4和5。
1. 选择&#x200B;**[!UICONTROL 保存]**。

>[!BEGINSHADEBOX]

观看演示视频，请参阅![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [添加组件描述](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/intro-to-analytics/customizing-the-ui/adding-dimension-and-metric-descriptions){target="_blank"}。

>[!ENDSHADEBOX]


## 数据词典 {#add-descriptions}

Analysis Workspace 中的数据词典可帮助用户和管理员跟踪并更好地了解其 Analytics 环境中的组件。 数据字典允许Analytics管理员直接在Analysis Workspace中添加组件描述。

有关编辑数据字典中的组件描述的信息，请参阅[编辑数据字典中的组件条目](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)。

有关数据字典的一般信息，请参阅[数据字典概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)。

>[!MORELIKETHIS]
>
>[报表组件设置](/help/components/vrs/vrs-components.md)
>[数据字典组件条目](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 自动生成描述

{{release-limited-testing-section}}

Adobe Analytics可以使用创新型人工智能来为您编写描述，而不是手动编写每个描述。 您可以为单个组件生成说明，也可以同时为多个组件生成说明。

生成的描述：

* 长度不超过3个句子。
* 以Adobe使用AI ]**生成的文本**[!UICONTROL &#x200B;结尾，以便用户知道已生成描述。
* 可以在生成后进行编辑。

### 先决条件

在生成描述之前，您的组织必须同意某些创新型人工智能法律条款。 如果贵组织不同意这些术语，则用于生成描述的选项将灰显。 选择选项旁边的信息图标![信息](/help/assets/icons/InfoOutline.svg)以了解如何启用该功能，或与组织的管理员或Adobe帐户团队联系。

### 描述的生成方式

生成的描述基于组件的定义以及有关如何在报表包中使用组件的其他上下文，例如：

* 维度的排名最前的项目
* 经常与组件一起使用的组件

当计算量度或区段引用另一个区段时，生成的描述将说明引用区段的定义。

### 从各种位置生成描述

您可以在Adobe Analytics的以下区域中生成描述。 某些位置允许您为多个组件生成描述，而其他位置则没有。

选择一个位置以了解如何在该位置生成描述。

| 位置 | 支持的组件 | 单个组件 | 多个组件 |
| --- | --- | --- | --- |
| [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>维度</li><li>量度</li><li>计算量度</li><li>区段</li><li>日期范围</li></ul> | 是 | 是 |
| [区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md) | 区段 | 是 | 否 |
| [区段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md#action-bar) | 区段 | 否 | 是 |
| [计算量度生成器](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) | 计算量度 | 是 | 否 |
| [计算量度管理器](/help/components/calculated-metrics/workflow/cm-manager.md#action-bar) | 计算量度 | 否 | 是 |
| [日期范围生成器](/help/analyze/analysis-workspace/components/calendar-date-ranges/create.md#date-range-builder) | 日期范围 | 是 | 否 |
| [日期范围管理器](/help/analyze/analysis-workspace/components/calendar-date-ranges/manage.md#action-bar) | 日期范围 | 否 | 是 |

{style="table-layout:auto"}