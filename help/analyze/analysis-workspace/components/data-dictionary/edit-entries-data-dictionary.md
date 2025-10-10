---
description: Analysis Workspace 中的数据字典可帮助用户对各类组件进行归档与管理，包括其预期用途、是否已获批准、是否为重复项等信息。
title: 编辑数据词典中的条目
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 88%

---

# 编辑数据词典中的组件条目

Analytics 管理员可以为给定的报告包编辑数据词典中的组件条目。报告包的所有用户都可以看到所做的任何更改。

要编辑数据词典中的组件：

1. 前往包含要编辑组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;**数据词典**&#x200B;图标。（[访问数据字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary)中介绍了访问数据字典的备用方法。）

   显示“数据词典”窗口。

   ![数据词典管理员视图](assets/data-dictionary-admin.png)

1. 确保在下拉菜单中选择了正确的报告包。默认情况下，会显示您已在使用的报告包。

1. （可选）在搜索字段中，开始键入要编辑的组件的名称。

   组件的类型可以通过颜色和图标来识别。**维度** ![维度图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色的，**区段** ![区段图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是蓝色的，**日期范围** ![日期范围图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的，**指标** ![指标图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是绿色的。Adobe 图标表示计算指标模板或区段模板，计算器图标 ![计算器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 表示由您组织的 Analytics 管理员创建的计算指标。

1. （可选）选择&#x200B;**过滤**&#x200B;图标![，即“数据词典过滤”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然后选择以下任一过滤器选项过滤组件列表：

   | 选项 | 功能 |
   |---------|----------|
   | **[!UICONTROL 已批准]** | 仅限管理员标记为“已批准”的组件。 |
   | **[!UICONTROL 收藏夹]** | 仅限收藏夹列表中的组件。 有关将组件添加到收藏夹列表的信息，请参阅[组件概述](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
   | **[!UICONTROL 维度]** | 仅限属于维度的组件。 （当您首次访问数据词典时，此选项也可在&#x200B;**[!UICONTROL 快速过滤]**&#x200B;选项卡中使用。） |
   | **[!UICONTROL 量度]** | 仅限属于量度的组件。 （当您首次访问数据词典时，此选项也可在&#x200B;**[!UICONTROL 快速过滤]**&#x200B;选项卡中使用。） |
   | **[!UICONTROL 区段]** | 仅限属于区段的组件。 （当您首次访问数据词典时，此选项也可在&#x200B;**[!UICONTROL 快速过滤]**&#x200B;选项卡中使用。） |
   | **[!UICONTROL 日期范围]** | 仅限属于日期范围的组件。 （当您首次访问数据词典时，此选项也可在&#x200B;**[!UICONTROL 快速过滤]**&#x200B;选项卡中使用。） |
   | **[!UICONTROL 显示所有]** | 所有组件。 仅管理员有此选项可用。 |
   | **[!UICONTROL 未批准]** | 仅限管理员尚未标记为已批准的组件。 作为管理员，这有助于确定需要您审阅和批准的组件。仅管理员有此选项可用。 |
   | **[!UICONTROL 缺少描述]** | 仅限说明字段中还没有说明的组件。 仅管理员有此选项可用。 |
   | **[!UICONTROL 显示重复项]** | <p>仅限与选定报表包中其他组件的名称相同或定义相同的组件。 名称或定义必须完全匹配才能显示为重复项。</p><p>仅管理员有此选项可用。</p><p>**注意：**&#x200B;对于定义，此选项包括您创建的组件和 Adobe 提供的组件。对于名称，此选项当前仅包括您创建的组件，而不包括 Adobe 提供的组件。将在未来的版本中添加显示 Adobe 提供的组件的重复名称。</p> |
   | **[!UICONTROL 没有最近的数据]** | 仅限过去90天内未收集任何数据的组件。 仅管理员有此选项可用。 |
   | **[!UICONTROL 由Adobe创建]** <!-- I don't see this option--> | 仅显示由Adobe创建的组件。  例如Adobe Target。 不会显示由管理员或您组织中的其他用户创建的组件。 |

   {style="table-layout:auto"}

1. （可选）选择&#x200B;**排序**&#x200B;图标![对组件图标进行排序](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任一过滤器选项对组件列表进行排序：

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **建议**] | 为组件排序，将推荐的组件置于列表的顶部。您或您组织中的其他人最频繁且最近使用的组件显示在列表的较高位置。 |
   | [!UICONTROL **按字母顺序**] | 按字母顺序为组件排序。 |
   | [!UICONTROL **分类**] | 根据组件类型（维度、指标、细分、日期范围）为组件排序。 |

   {style="table-layout:auto"}

1. 从组件列表中，选择要编辑的组件。

1. 选择组件名称旁边的&#x200B;**编辑**&#x200B;图标，即![“数据词典编辑”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)。

1. 编辑有关组件的以下任何信息：

   | 选项 | 功能 |
   |---------|----------|
   | **[!UICONTROL 已批准]** | <p>表示该组件已获管理员审阅和批准。</p><p>在组件获得批准后，管理员可通过选择&#x200B;**已批准**&#x200B;按钮而撤销批准。</p> |
   | **[!UICONTROL 需要批准]** | <p>表示该组件尚未获得管理员审阅和批准。</p><p>管理员会看到&#x200B;**[!UICONTROL 批准]**&#x200B;选项。 选择此选项会为用户将组件标记为“已批准”。</p> |
   | **[!UICONTROL 描述]** | 描述组件的预期功能。（此信息由 Analytics 管理员添加，如[添加组件描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)中所述。） |
   | **[!UICONTROL 常常与以下组件一同使用]** | <p>显示最常与您正在查看的组件一起使用的组件。</p><p>在 5 种主要组件类型中，最多显示 5 个组件：量度、计算量度、维度、区段和日期范围。</p><p>此列表基于过去 90 天的数据。其中仅列出您有权查看的组件。</p><p>管理员可通过在&#x200B;**[!UICONTROL 始终包括]**&#x200B;和&#x200B;**[!UICONTROL 始终排除]**&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您编排用户可看到的组件之前，请首先应用&#x200B;**全部显示**&#x200B;过滤器以确保您可看到任何不与您共享的组件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | **[!UICONTROL 类似于]** | <p>显示与您正在查看的组件名称类似的组件。</p><p>在 5 种主要组件类型中，最多显示 5 个组件：量度、计算量度、维度、区段和日期范围。</p><p>其中仅列出您有权查看的组件。</p><p>此处还显示报告包中任何重复的组件。Analytics 管理员应识别并删除所有重复的组件，如[监视数据词典运行状况](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理员可通过在&#x200B;**[!UICONTROL 始终包括]**&#x200B;和&#x200B;**[!UICONTROL 始终排除]**&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您编排用户可看到的组件之前，请首先应用&#x200B;**全部显示**&#x200B;过滤器以确保您可看到任何不与您共享的组件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：**&#x200B;**类似于**&#x200B;部分当前仅包括您创建的组件，而不包括 Adobe 提供的组件。将在未来的版本中添加 Adobe 提供的组件。</p> |
   | **[!UICONTROL 标记]** | 显示应用于组件的所有标记。具有管理员访问权限的用户可以在编辑组件时添加标记。 |
   | **[!UICONTROL 组件类型]** | 列出组件的类型，无论是维度、量度、区段还是日期范围。 |
   | **[!UICONTROL 创建者]** | 显示创建组件的用户名称。 |
   | **[!UICONTROL 预览]** | 显示组件在 Analysis Workspace 中的外观预览。 |
   | **[!UICONTROL 上次修改日期]** | 显示上次修改组件的日期。在查看区段、计算量度和日期范围时将显示此部分。 |

   {style="table-layout:auto"}

1. 单击&#x200B;**保存**&#x200B;图标，即![“数据词典保存”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg)来保存您的更改。
