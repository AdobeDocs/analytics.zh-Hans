---
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 93%

---
# 片段

## Reports &amp; Analytics 生命周期结束公告 {#ra-eol}

>[!IMPORTANT]
>
>自&#x200B;**2024年1月17日起**，Adobe已停用Reports &amp; Analytics及其随附的报告和功能。 届时，Reports &amp; Analytics及其所有报表和计划都将停止工作。 支持 Reports &amp; Analytics 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。在 Analysis Workspace 中提供了 Reports &amp; Analytics 的大部分功能。有关在Analysis Workspace中使用报表的信息，请参阅[使用预建报表](/help/analyze/analysis-workspace/reports/use-reports.md)。
> 
>自 2015 年发布 Analysis Workspace 以来，Reports &amp; Analytics 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。本通知解释了生命周期结束的过程。
>
>详细了解 Reports &amp; Analytics [生命周期结束公告](https://www.adobe.com/go/analytics_rnaeol_cn)。

## 数据词典过滤条件 {#dd-filter-criteria}

1. （可选）选择&#x200B;**过滤**&#x200B;图标![，即“数据词典过滤”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然后选择以下任一过滤器选项过滤组件列表：

| 选项 | 功能 |
|---------|----------|
| [!UICONTROL **已批准**] | 仅显示标记为由管理员批准的组件。 |
| [!UICONTROL **收藏夹**] | 仅显示收藏夹列表中的组件。有关将组件添加到收藏夹列表的信息，请参阅[组件概览](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
| [!UICONTROL **维度**] | 仅显示维度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
| [!UICONTROL **量度**] | 仅显示量度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
| [!UICONTROL **区段**] | 仅显示区段的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。）<!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **日期范围**] | 仅显示日期范围的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
| [!UICONTROL **显示所有**] | 显示所有组件。仅管理员有此选项可用。 |
| [!UICONTROL **未批准**] | 仅显示未标记为由管理员批准的组件。作为管理员，这有助于确定需要您审阅和批准的组件。仅管理员有此选项可用。 |
| [!UICONTROL **缺少描述**] | 仅显示在“描述”字段中尚未描述的组件。仅管理员有此选项可用。 |
| [!UICONTROL **显示重复项**] | <p>仅显示与所选报告包中的另一组件同名或定义相同的组件。名称或定义必须完全匹配才能显示为重复项。</p><p>仅管理员有此选项可用。</p><p>**注意：**&#x200B;对于定义，此选项包括您创建的组件和 Adobe 提供的组件。对于名称，此选项当前仅包括您创建的组件，而不包括 Adobe 提供的组件。将在未来的版本中添加显示 Adobe 提供的组件的重复名称。</p> |
| [!UICONTROL **没有最近的数据**] | 仅显示在过去 90 天内未收集任何数据的组件。仅管理员有此选项可用。 |
| [!UICONTROL **由Adobe创建**] <!-- I don't see this option--> | 仅显示由 Adobe 创建的组件。不会显示由管理员或您组织中的其他用户创建的组件。 |

{style="table-layout:auto"}

## “数据词典”组件信息 {#dd-component-information}

| 选项 | 功能 |
|---------|----------|
| [!UICONTROL **已批准**] | <p>表示该组件已获管理员审阅和批准。</p><p>在组件获得批准后，管理员可通过选择&#x200B;**已批准**&#x200B;按钮而撤销批准。</p> |
| [!UICONTROL **需要批准**] | <p>表示该组件尚未获得管理员审阅和批准。</p><p>管理员会看到&#x200B;[!UICONTROL **批准**]&#x200B;选项。 选择此选项会为用户将组件标记为“已批准”。</p> |
| [!UICONTROL **描述**] | 描述组件的预期功能。（此信息由 Analytics 管理员添加，如[添加组件描述](/help/analyze/analysis-workspace/components/add-component-descriptions.md)中所述。） |
| [!UICONTROL **常常与以下组件一同使用**] | <p>显示最常与您正在查看的组件一起使用的组件。</p><p>在 5 种主要组件类型中，最多显示 5 个组件：量度、计算量度、维度、区段和日期范围。</p><p>此列表基于过去 90 天的数据。其中仅列出您有权查看的组件。</p><p>管理员可通过在&#x200B;[!UICONTROL **始终包括**]&#x200B;和&#x200B;[!UICONTROL **始终排除**]&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您编排用户可看到的组件之前，请首先应用&#x200B;**全部显示**&#x200B;过滤器以确保您可看到任何不与您共享的组件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **类似于**] | <p>显示与您正在查看的组件名称类似的组件。</p><p>在 5 种主要组件类型中，最多显示 5 个组件：量度、计算量度、维度、区段和日期范围。</p><p>其中仅列出您有权查看的组件。</p><p>此处还显示报告包中任何重复的组件。Analytics 管理员应识别并删除所有重复的组件，如[监视数据词典运行状况](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理员可通过在&#x200B;[!UICONTROL **始终包括**]&#x200B;和&#x200B;[!UICONTROL **始终排除**]&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您编排用户可看到的组件之前，请首先应用&#x200B;**全部显示**&#x200B;过滤器以确保您可看到任何不与您共享的组件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：****类似于**&#x200B;部分当前仅包括您创建的组件，而不包括 Adobe 提供的组件。将在未来的版本中添加 Adobe 提供的组件。</p> |
| [!UICONTROL **标记**] | 显示应用于组件的所有标记。具有管理员访问权限的用户可以在编辑组件时添加标记。 |
| [!UICONTROL **组件类型**] | 列出组件的类型，无论是维度、量度、区段还是日期范围。 |
| [!UICONTROL **创建者**] | 显示创建组件的用户名称。 |
| [!UICONTROL **预览**] | 显示组件在 Analysis Workspace 中的外观预览。 |
| [!UICONTROL **上次修改日期**] | 显示上次修改组件的日期。在查看区段、计算量度和日期范围时将显示此部分。 |

{style="table-layout:auto"}

## 组件排序选项 {#components-sort-options}

| 选项 | 功能 |
|---------|----------|
| [!UICONTROL **建议**] | 为组件排序，将推荐的组件置于列表的顶部。您或您组织中的其他人最频繁且最近使用的组件显示在列表的较高位置。 |
| [!UICONTROL **按字母顺序**] | 按字母顺序为组件排序。 |
| [!UICONTROL **分类**] | 根据组件类型（维度、指标、细分、日期范围）为组件排序。 |

{style="table-layout:auto"}

## 发布的有限测试阶段 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。

## 发布的有限测试阶段部分 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本部分描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。


## 插件免责声明 {#plug-in}

>[!IMPORTANT]
>
>此插件由 Adobe Consulting 团队提供，旨在帮助您从 Adobe Analytics 中获取更多的价值。Adobe 客户关怀团队不提供对此插件的支持，包括安装或疑难解答。如果您需要关于此插件的帮助，请与您组织的 Adobe 客户团队联系。他们可为您安排与顾问会面以寻求帮助。


## 仅适用于现有客户 {#available-existing-customers}

>[!AVAILABILITY]
>
>本节中介绍的功能仅适用于已获得相应功能许可证的现有客户。 此功能不再作为现有或新客户的附加组件提供。
>
