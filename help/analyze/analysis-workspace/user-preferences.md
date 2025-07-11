---
title: 用户偏好设置
description: 了解如何为用户设置常规偏好和项目偏好。
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
source-git-commit: 6cec1085093404235e29319db984d4389c68c31e
workflow-type: ht
source-wordcount: '3461'
ht-degree: 100%

---

# 用户偏好设置

可以为创建的所有新项目或面板管理 Analysis Workspace 及其相关组件的设置。现有项目和面板不受影响。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [管理偏好设置](https://video.tv.adobe.com/v/3429988/?quality=12&learn=on&captions=chi_hans){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]

## 更新偏好设置

您可以通过以下方式更新您的偏好设置：

- 从 Workspace 主界面选择 ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 编辑偏好设置]**。
- 在 Workspace 项目中工作时，从菜单中选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 用户偏好设置]**。
- 从 Customer Journey Analytics 的顶部菜单栏中选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 偏好设置]**（仅适用于产品管理员）。

## 配置偏好设置

您可以配置以下偏好设置：


## 常规偏好设置

您可以为在 Analysis Workspace 中创建的所有新项目自定义常规偏好设置。有关如何访问这些偏好设置的信息，请参阅[更新偏好设置](#update-preferences)。

| 偏好设置 | 选项 |
| --- | --- |
| 登陆页面 | 选择访问 Adobe Analytics 时显示为默认页面的页面： <ul><li>项目列表（默认）</li><li>空白项目</li><li>从列表中选择的具体项目</li></ul> |
| 显示提示 | 在 Analysis Workspace 右下方区域的蓝色框中显示提示。 <p>默认启用选项。</p> |
| 左边栏组中显示的组件 | 选择要在左边栏的“组件”菜单中显示的每个组件的数量。 <p>如果选择 0，则无法再从工作区的左边栏访问该组件。</p><p>默认情况下，为以下各项显示 5 个组件：</p> <ul><li>维度</li><li>量度</li><li>过滤器</li><li>日期范围</li></ul> <p>有关 Analysis Workspace 中组件的更多信息，请参阅[组件概述](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。</p> |

## 公司偏好设置 {#company-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="仅允许与 Workspace 用户共享"
>abstract="启用后，**[!UICONTROL 与任何人共享]**&#x200B;选项在共享 Analysis Workspace 项目时将不再可供用户使用。之前通过此共享选项获得项目访问权限的人员将无法再访问该项目。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="需要 Experience Cloud 身份验证"
>abstract="启用后，通过 Analysis Workspace 中的&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;选项获得项目访问权限的人员必须使用其 Experience Cloud 凭据进行身份验证。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="允许对项目进行评论"
>abstract="启用后，Analysis Workspace 中每个项目的右侧栏中会显示一个评论区域。"


您可以更新适用于组织内所有用户和项目的公司偏好设置。有关如何访问这些偏好设置的信息，请参阅[更新偏好设置](#update-preferences)。

| 部分 | 偏好设置 | 选项 |
| --- | --- | --- |
| **模板选项卡** | | |
|  | 隐藏“模板”选项卡 | 隐藏您组织内所有用户的“模板”选项卡。 |
| **项目共享** | | |
| | 仅允许与 Workspace 用户共享 | 启用此选项后，组织内的用户将无法在&#x200B;**[!UICONTROL 共享]**&#x200B;菜单中看到&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;选项。用户无法与已在您的组织中拥有 Analysis Workspace 帐户的人员共享项目，如[与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link)中所述。<br/>此选项默认对所有组织处于禁用状态，拥有 Healthcare Shield 授权的客户除外。 <p>在启用或禁用此选项时，请考虑以下事项：<ul><li>启用此选项后，之前通过&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;共享选项获得项目访问权限的人员将无法再访问该项目。</li><li>如果启用此选项（仅允许与 Workspace 用户共享），然后将其禁用（允许与任何人共享），则之前通过&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;共享选项获得项目访问权限的人员不会自动重新获得对项目的访问权限。在这种情况下，已共享项目的用户必须启用在与任何人共享项目时可用的&#x200B;[!UICONTROL **链接已激活**]&#x200B;选项&#x200B;**（[!UICONTROL 共享]** > **[!UICONTROL 与任何人共享]**），如[与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link)中所述。</li><li>**对于许可 Healthcare Shield 的客户：**&#x200B;该选项默认启用且无法禁用。在禁用此选项以便用户可以使用&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;的共享选项之前，您首先需要在 Adobe Admin Console 中添加[!UICONTROL 与任何人共享项目链接]权限（位于[!UICONTROL 报告工具]下）。添加权限后，您可以禁用此选项，然后接受由此产生的法律声明。有关如何在 Admin Console 中添加权限的信息，请参阅[在 Admin Console 中管理产品权限](https://helpx.adobe.com/cn/enterprise/using/manage-permissions-and-roles.html)。</li></ul> |
| | 需要 Experience Cloud 身份验证 | 启用此选项后，通过 Analysis Workspace 中的&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;选项获得项目访问权限的人员必须使用其 Experience Cloud 凭据进行身份验证。<p>启用此选项后，当用户使用&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;共享选项来共享项目时，共享对话框中都会启用&#x200B;**[!UICONTROL 需要 Experience Cloud 身份验证]**&#x200B;选项，并且共享项目的用户无法禁用该选项。有关用户如何与任何人共享项目的信息，请参阅[与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link)。 <p> <p>启用此选项时，请考虑以下事项： <ul><li>启用此选项后，所有之前通过&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;共享选项共享且未启用[!UICONTROL 需要 Experience Cloud 身份验证]选项的项目都将被停用。<p>如果启用此选项（以要求进行 Experience Cloud 身份验证），然后将其禁用（以允许拥有链接的任何人员访问项目），则之前通过&#x200B;**[!UICONTROL 与任何人共享]**&#x200B;共享选项获得项目访问权限的人员不会自动重新获得对项目的访问权限。在这种情况下，已共享项目的用户必须启用在与任何人共享项目时可用的[!UICONTROL 链接已激活]选项&#x200B;**（[!UICONTROL 共享]** > **[!UICONTROL 与任何人共享]** > **[!UICONTROL 链接已激活]**），如[与任何人共享项目（无需登录）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link)中所述。</li><li>仅在组织内实施 SSO 后，此选项才可用。有关系统管理员如何为组织启用 SSO 的信息，请参阅[设置身份标识和单点登录](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html)。</p><p>如果已为组织配置 SSO，请检查控制台中是否实施了任何类型的自动帐户创建。通常，系统管理员会进行此设置，如[启用自动帐户创建](https://helpx.adobe.com/cn/enterprise/using/automatic-account-creation.html)中所述。</li><li>如果您的组织许可 Healthcare Shield，则默认情况下会启用此选项且无法禁用。</li></ul> |

{style="table-layout:auto"}

## 项目和分析偏好设置 {#project-analyses-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="分类调色板"
>abstract="应用于 Analysis Workspace 和引导式分析中的许多可视化功能。每种颜色代表不同的类别值。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="发散调色板"
>abstract="应用于 Analysis Workspace 和用户增长引导式分析中的群组表。该调色板具有数字含义，其中带有两个极端以及中间的基线。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="顺序调色板"
>abstract="应用于频率趋势（堆积条）引导式分析。该调色板具有从浅到深的数字含义。"

您可以为在 Analysis Workspace 中创建的所有新项目自定义项目偏好设置。有关如何访问这些偏好设置的信息，请参阅[更新偏好设置](#update-preferences)。

其中部分偏好设置也可针对单个项目进行自定义，具体说明请参见[项目概述](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。

单击链接的偏好设置标题以获取有关每个偏好设置的更多信息和上下文。

| 部分 | 偏好设置 | 选项 |
| --- | --- | --- |
| **显示** | | |
|  | [视图密度](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | 通过减小左侧边栏、自由格式表和同类群组表的垂直边距，让您可在屏幕上选择显示内容的多少。 <ul><li>紧凑</li><li>舒适</li><li>展开（默认）</li></ul> |
| | [调色板](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | 选择 Analysis Workspace 中使用的可视化调色板。<ul><li>**分类调色板**：适用于 Analysis Workspace 中的许多可视化图表。每种颜色均代表不同的分类值。从 Adobe 提供的选项中进行选择，或输入由逗号分隔的十六进制值定义的自定义调色板。</li><li>**发散调色板**：适用于 Analysis Workspace 中的同类群组表。此调色板包含两个极端和中间基线的数值含义。</li><li>**顺序调色板**：适用于频率趋势（堆叠柱状图）引导分析。此调色板包含从浅色到深色的数值含义。</li></ul> |
| **数据** | | |
|  | [报告包](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/panels) | 选择表格和可视化从中获取数据的位置。 <ul><li>最近（默认）</li><li>从列表中选择特定报告包</li></ul> |
|  | [日历](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/panels) | 从以下列表中选择： <ul><li>Adobe 提供的范围（默认为“本月”）</li><li>自定义范围</li></ul> |
|  | [面板类型](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/panels) | <ul><li>自由格式（默认）</li><li>空白</li><li>快速洞察</li></ul> |
|  | 计数重复实例 | 指定是否将重复实例计入报告中。例如，此设置（激活时）会将同一页面的多次连续页面查看视为多次页面查看。关闭它后，它们将计为单个页面视图。 <p>**注意：**&#x200B;此设置仅影响某些量度（例如单页访问），不适用于流量或流失可视化。</p> |
|  | 数字格式 | <ul><li>1,000.00（默认）</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV 分隔符字符 | <ul><li>逗号（默认）</li><li>分号</li><li>冒号</li><li>竖线</li><li>句点</li><li>空格</li><li>制表符</li></ul> |
|  | 显示注释 | 选择注释是否在您的项目中可见。有关注释的更多信息，请参阅[注释概述](/help/analyze/analysis-workspace/components/annotations/overview.md)。 |

## 自由格式表偏好设置 {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="显示异常"
>abstract="选择&#x200B;**[!UICONTROL 显示异常]**&#x200B;后，系统会自动对添加到时间序列自由格式表格可视化中的首个量度列执行异常检测。"

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="显示预测"
>abstract="选择&#x200B;**[!UICONTROL 显示预测]**&#x200B;将会自动对已添加到时间序列自由格式表可视化图表中的第一个量度列进行预测。"


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="默认表量度"
>abstract="选择用于自由格式表的默认量度。如果选定的数据视图不包含所选的默认量度，表格将自动切换到另一个主要量度。"


您可以为在 Analysis Workspace 中创建的所有新项目自定义自由格式表偏好设置。有关如何访问这些偏好设置的信息，请参阅[更新偏好设置](#update-preferences)。

这些相同的偏好设置中的一些也可以针对单个表进行自定义。

单击链接的分区标题以获取有关可用偏好设置的更多信息和上下文。

| 部分 | 偏好设置 | 选项 |
| --- | --- | --- |
| **表格** | | |
| | 表类型 | <ul><li>自由格式表</li><li>表生成器</li></ul> |
| | 默认表量度 | <ul><li>发生次数</li><li>独特访客</li><li>访问次数</li></ul> |
| | 默认表维度 | 从分钟、小时、天、周、月、季度或年中选择。 |
| | 调整日期 | 选择此选项可将每列的日期与同一行的所有开始日期对齐。 |
| **[列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | 隐藏标头文本 | 让自由格式表中的标题文本换行，以使标题更加易读，表格更易共享。换行对 PDF 渲染和名称较长的量度非常有用。默认处于启用状态。 |
| | 显示总数 | 此总数通常等于[!UICONTROL 全部总计]或者为其一部分。它反映自由格式表内应用的任何表筛选器，包括[!UICONTROL 不包含任何内容]选项。 |
| | 显示总计 | 此总计表示已收集的所有点击数，有时候称为&#x200B;*报告包总计*。当在面板级别或自由格式表中应用区段时，此总计会进行相应的调整以反映符合区段标准的所有点击。带有[统计行](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)的表或细分不支持全部总计。 |
| | 显示迷您图 | 在图表底部显示或隐藏线形图。隐藏时，图例更改为不再在视觉上参照线形图。 |
| | 数值 | 确定单元格是否显示/隐藏量度的数值。例如，如果量度是“页面查看次数”，则数值是行项目的页面查看次数。 |
| | 百分比 | 确定单元格是否显示/隐藏量度的百分比值。例如，如果量度是“页面浏览次数”，则百分比值等于行项目的页面浏览次数除以该列的总页面浏览次数。注意：为确保更高的准确性，有时会显示超过 100% 的百分比。上限已提升至 1000%，以确保列宽在必要时可以扩展到更大的尺寸。 |
| | 显示异常 | 确定此列中的值是否要运行异常检测。 |
| | 将零解释为没有值 | 对于具有 0 值的单元格，确定将其显示为 0 还是空白单元格。当您查看一个月中每一天的数据，而有些天尚未发生时，这非常有用。可以为将来日期显示空白单元格，而不是 0。图表也会遵循此设置（即在启用该设置时，不会显示值为 0 的线条或柱状图）。 |
| | 背景 | 确定单元格是否显示/隐藏所有单元格格式，包括条形图和条件格式。 <ul><li>条形图</li> 一张水平条形图，用于表示该单元格的数值相对于整列总值的占比。 <li>条件格式</li>有关条件格式的详细信息，请参阅[列设置](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的“条件格式”</ul> |
| | 单元格预览 | 预览每个单元格在应用当前选定的格式选项后的显示效果。 |
| **[行](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | 按位置划分 | 如果您希望细目分类保留在项目的位置而不是项目本身，请选择此选项。有关细分的更多信息，请参阅[细分维度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。 |
| | 百分比计算 | <ul><li>列</li><li>行</li></ul> |
| | 列总计（仅限静态行） | <ul><li>显示行总和：显示各个行项目的总和 </li><li>显示总计：显示进行重复数据删除后的行总和。</li></ul> |

## 可视化偏好设置

您可以更新在 Analysis Workspace 中创建的所有新项目的可视化偏好设置。有关如何访问这些偏好设置的信息，请参阅[更新偏好设置](#update-preferences)。

这些相同的偏好设置中的一些也可以针对单个可视化进行自定义。

单击链接的分区标题以获取有关可用偏好设置的更多信息和上下文。

| 部分 | 偏好设置 | 选项 |
| --- | --- | --- |
| **常规默认值** | | |
| | 百分比 | 以百分比显示所有可视化的值。 |
| | 图例可见 | 用于隐藏所有可视化的详细图例文本。 |
| | 限制最大项目数 | 减少所有可视化的 X 轴上的项目数。如果您有大型数据集，这会很有用。 |
| | 显示双轴（适用时） | 仅在包含两个量度时适用 —— 其中一个量度使用左侧 y 轴，另一个量度使用右侧 y 轴。当绘制的量度数量级相差较大时，此设置非常有用。 |
| | 标准化（适用时） | 要求所有量度按等比例计算。当绘制的量度数量级相差较大时，此设置非常有用。 |
| | 将 Y 轴定位在零 | 如果图表上绘制的所有值都远远大于零，图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设为零（并将重新绘制图表）。 |
| | 允许异常缩放 Y 轴 | 如果图表中有多个量度，则必须将鼠标悬停在每个异常上以查看该量度的置信区间。为了使可视化更清晰，异常检测置信区间不会自动缩放 y 轴。此选项允许置信区间缩放可视化。 <p>有关详细信息，请参阅 Analysis Workspace 中的[查看异常情况](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md)。</p> |
| **[线形图](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | 百分比 | 以百分比显示线条可视化的值。 |
| | 图例可见 | 隐藏折线图可视化的详细图例文本。 |
| | 限制最大项目数 | 减少直线可视化中 X 轴上的项目数。当数据集较大时，此设置非常有用。 |
| | 显示双轴（适用时） | 仅在包含两个量度时适用 —— 其中一个量度使用左侧 y 轴，另一个量度使用右侧 y 轴。当绘制的量度数量级相差较大时，此设置非常有用。 |
| | 标准化（适用时） | 要求所有量度按等比例计算。当绘制的量度数量级相差较大时，此设置非常有用。 |
| | 显示 X 轴 | 在线形图上显示 x 轴。 |
| | 显示 Y 轴 | 在线形图上显示 y 轴。 |
| | 锚 Y 轴 | 如果图表上绘制的所有值都远远大于零，图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设为零（并将重新绘制图表）。 |
| | 显示最小值 | 叠加最小值标签以快速突出显示量度中的谷值。注意：最小值派生自可视化图表中的可见数据点，而不是维度中的完整值集。 |
| | 显示最大值 | 叠加最大值标签以快速突出显示量度中的峰值。注意：最大值派生自可视化图表中的可见数据点，而不是维度中的完整值集。 |
| | 显示趋势线 | 显示线系列的回归或均线。趋势线有助于在数据中描绘更清晰的图案。 |
| **[同类群组](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | 粒度 | 对于趋势性可视化图表，您可以更改时间粒度（日、周、月、季度或年）。此更改也适用于数据源表。 |
| | 仅显示百分比 | 删除数值，仅显示百分比。 |
| | 将百分比四舍五入到最接近的整数 | 将百分比值舍入为最接近的整数，而不是显示十进制值。 |
| | 显示平均百分比行 | 在表顶部插入新行，然后添加每列中值的平均值。 |
| | 队列预览 | 预览调色板在队列可视化图表中的显示方式。 |
| | 同类群组调色板 | 队列可视化图表中使用的调色板。 |
| **[组合图表](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | 显示 X 轴 | 在组合图表上显示 x 轴。 |
| | 显示 Y 轴 | 在组合图表上显示 y 轴。 |
| | 在线上显示杠铃 | 在组合图表中的线条上显示杠铃。 |
| **[关键量度摘要](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | 摘要显示类型 | <ul><li>强调百分比变化</li><li>强调数值</li></ul> |
| | 显示迷您图 | 在图表底部显示或隐藏线形图。隐藏时，图例更改为不再在视觉上参照线形图。 |
| | 在迷您图上显示最大值和最小值 | 在主线形图和比较线形图上显示最小值和最大值。 |
| | 显示比较 | 显示对比数据。隐藏时，比较线形图和摘要变化对象在视图中隐藏。 |
| | 数值选项 | 在&#x200B;[!UICONTROL **关键量度摘要**]&#x200B;部分 <ul><li>显示百分比变化</li><li>显示原始差异</li>主要日期范围和次要日期范围中量度的总值之间的原始差异</ul> |
| **[流失](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | 容器 | 在“访问次数”和“访客”之间切换，以分析访客路径。默认值为“访客”。这些设置可帮助您在访客级别（跨访问）了解访客参与程度，或将分析限定于单次访问。 <p>可以使用以下选项：</p> <ul><li>访问</li><li>访客</li></ul> |
| **[流](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | 容器 | 在&#x200B;[!UICONTROL **流**]&#x200B;部分 <ul><li>访问</li><li>访客</li></ul> |
| | 包装标签 | 通常情况下，流量元素上的标签会被截断以节约屏幕资源，但您可以通过选中此框使整个标签可见。默认值 = 取消选中。 |
| | 包括重复实例 | 流量可视化图表基于某个维度的实例。此设置使您可以选择包含还是排除重复实例，例如页面重新载入。但是，不能从包含多值维度（例如 listVar、listProp、s.product、推销 eVar 等）的流量可视化图表中删除重复项。默认值 = 取消选中。 |
| | 显示工具提示 | 确定将光标悬停在流量可视化图表中的各个节点上时是否显示包含节点数据的工具提示。 |
| | 列数 | 确定在流量图中需要多少列。 |
| | 每列扩展的项 | 每列中需要多少项。 |
| **堆栈图** | | |
| | 100% 堆叠 | 在面积堆叠、条形堆叠或水平条形堆叠的可视化图表上的此设置将图表转换为“100% 堆叠”的可视化图表。 <p>如需了解更多信息，请参阅[条形图和堆叠的条形图](/help/analyze/analysis-workspace/visualizations/bar.md)。</p> |
| **[直方图](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | 存储体数量 | 在可视化中选择数据范围（储存体）的数量。存储段的最大数量为 50。 <p>有关更多信息，请参阅[直方图](/help/analyze/analysis-workspace/visualizations/histogram.md)。</p> |
| | 计算方法 | 从以下选项中进行选择： <ul><li>点击</li><li>访问</li><li>访客</li></ul> <p>例如，结合页面浏览量使用时，您可以选择“每位访客的页面浏览量”、“每次访问的页面浏览量”或“每次点击的页面浏览量”。对于点击来说，“发生次数”可作为自由格式表中的 y 轴量度。</p> |
| **[地图](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | 绘制维度图 | <ul><li>移动经度/纬度</li><li>地理维度</li></ul> |
| | 地图类型 | <ul><li>气泡</li><li>热图</li></ul> |
| | 颜色主题 | 从珊瑚色、红色、绿色、蓝色、热图和正/负中进行选择。 |
| | 地图样式 | 从基本、街道、明亮、浅色、深色和卫星中进行选择。 |
| **[摘要变化](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 值 | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>比例更改</li><li>原始差异</li></ul> |
| | 百分比 | 以百分比显示摘要更改可视化效果的值。 |
| | 图例可见 | 此设置允许您为摘要变化可视化图表隐藏详细的图例文本。 |
| | 缩写值 | 选中后，可指定小数位数。 |
| **[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | 百分比 | 以百分比显示摘要编号可视化的值。 |
| | 图例可见 | 用于隐藏摘要编号可视化的详细图例文本。 |
| | 值汇总方式 | 从最大值、最小值、平均值、中值和总和中进行选择。 |
| | 缩写值 | 选中后，可指定小数位数。 |
| **[树状图](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | 百分比 | 以百分比显示 Treemap 可视化的值。 |
| | 限制最大项目数 | 减少树状图可视化中 X 轴上的项目数。如果您有大型数据集，这会很有用。 |
| **[维恩图](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | 图例可见 | 允许您为维恩图可视化隐藏详细的图例文本。 |
| **[散点图](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | 百分比 | 以百分比显示散点图可视化的值。 |
| | 图例可见 | 允许您为散点图可视化隐藏详细的图例文本。 |
| | 限制最大项目数 | 减少散点图可视化中 X 轴上的项目数。如果您有大型数据集，这会很有用。 |
| | 将 Y 轴定位在零 | 如果图表上绘制的所有值都远远大于零，图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设为零（并将重新绘制图表）。 |

## 恢复默认偏好设置

您可以将所有用户偏好设置恢复为系统默认值。此选项不会影响&#x200B;**[!UICONTROL 公司]**&#x200B;选项卡下的管理员偏好设置。此操作无法撤销。

1. 在 Adobe Analytics 中，从顶部菜单中选择&#x200B;[!UICONTROL **组件**] **>** [!UICONTROL **偏好设置**]。或者从 Workspace 菜单中选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 用户设置]**。

1. 在右上角，选择&#x200B;**[!UICONTROL 恢复默认]**。

1. 在&#x200B;**[!UICONTROL 恢复系统默认设置]**&#x200B;中选择&#x200B;**[!UICONTROL 恢复默认值]**。

## [!UICONTROL 深色主题]

如果您更希望为 Customer Journey Analytics 用户界面使用深色背景，可以切换到[!UICONTROL 深色主题]。

1. 选择右上角的 Experience Cloud 用户图标。

   ![dark-theme](assets/dark-theme.png)

1. 启用&#x200B;**[!UICONTROL 深色主题]**。

