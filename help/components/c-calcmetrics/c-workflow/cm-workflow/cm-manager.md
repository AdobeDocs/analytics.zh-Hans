---
description: “计算量度”页面提供了许多种管理量度的方式，如共享、筛选、标记、批准、复制、删除和标记为收藏。
title: 计算量度管理器
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: cfae0661dfa9c61daea33c3a52204793ce3d35c1
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 20%

---

# 计算量度管理器

“计算量度”页面提供了许多种管理量度的方式，如共享、筛选、标记、批准、复制、删除和标记为收藏。

“计算量度”页面会显示您拥有的以及与您共享的所有区段。 管理员级别的用户可以查看组织内的所有自定义指标。

<!-- add screenshot -->

## 访问计算量度管理器

1. 在Adobe Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **计算量度**].

## 计算量度管理器中的可用操作

在计算量度管理器中，您可以：

* [筛选计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [将计算量度标记为收藏内容](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [批准计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [标记计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [共享计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* 将计算量度导出到CSV文件。

* [复制计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* 删除计算量度

## 配置列

通过配置显示的列，可以配置在计算量度管理器中为每个计算量度显示的信息。

要在计算量度管理器中配置可见列，请执行以下操作：

1. 在Adobe Analytics中，选择 **[!UICONTROL 组件]** 选项卡，然后选择 **[!UICONTROL 计算量度]**.

1. 在计算量度管理器中，选择 **自定义列** 图标 ![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在计算量度管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 收藏 | 在每个计算量度旁边显示星形图标，以使您可将计算量度标记为收藏。 有关更多信息，请参阅 [将计算量度标记为收藏](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | 标题和描述 | 这些值在计算量度生成器中提供。 要编辑标题和描述，请选择标题链接以打开计算指标生成器。 |
   | 报表包 | 指示指标上次保存在哪个报表包中。 |
   | 所有者 | 指示谁拥有该自定义指标。如果您不是管理员，则只能看到您拥有的指标或与您共享的指标。 |
   | 标记 | 显示应用到指标的标记，这些标记由您自己或与您共享计算指标的人添加。 |
   | 共享对象 | 列出您与之共享计算指标的个人或组（仅限管理员）或全部（仅限管理员）。 <p>共享计算指标时，计算指标名称旁边会显示一个共享图标。</p> |
   | 修改日期 | 指示上次修改自定义量度的日期。 |
   | 用在 | 显示计算量度当前使用的组件数。 <p>例如，如果计算量度在40个项目和2个警报中使用，则此列的值显示为 [!UICONTROL **42个组件**]. <p>选择此列中的值可查看在其中使用计算量度的细分(例如， [!UICONTROL **项目(40)**]， [!UICONTROL **警报(2)**])。</p><p>计算量度可用于以下任何组件类型：</p> <ul><li>警报</li><li>项目</li><li>计划项目</li></ul><p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。</p><p>此信息不包括API、Report Builder或Data Warehouse的使用情况。</p><p>您可以使用 [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。</p><p>此 [!UICONTROL **使用位置**] 默认情况下不显示列。 [配置列](#configure-columns) 以显示。</p> |
   | 上次使用时间 | 显示计算指标上次在以下任意组件类型中使用的日期： <ul><li>警报</li><li>计算量度</li><li>项目</li><li>计划项目</li></ul> <p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。</p><p>此信息不包括API、Report Builder或Data Warehouse的使用情况。</p><p>您可以使用 [数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。 |

   {style="table-layout:auto"}
