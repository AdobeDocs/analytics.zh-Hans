---
source-git-commit: f66686838b341b57256932d65e6b0dd005205b0d
workflow-type: tm+mt
source-wordcount: '2910'
ht-degree: 87%

---
# 片段

## 旧版 Report Builder {#legacy-arb}

>[!IMPORTANT]
>
>2024年10月16日发布了新的、简化的[Report Builder](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/rb-overview)。 它在Mac、Windows和Web浏览器上受支持。
>&#x200B;>此旧版Report Builder加载项版本仍然有效。 您可以[将旧工作簿](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/report-builder/convert-workbooks)转换为新的Report Builder。

## Reports & Analytics 生命周期结束公告 {#ra-eol}

>[!IMPORTANT]
>
>自&#x200B;**2024年1月17日起**，Adobe已停用Reports &amp; Analytics及其随附的报告和功能。 届时，Reports &amp; Analytics及其所有报表和计划都将停止工作。 支持 Reports &amp; Analytics 的报告、可视化图表和底层技术不再满足 Adobe 的技术标准。在 Analysis Workspace 中提供了 Reports &amp; Analytics 的大部分功能。有关信息，请参阅[使用模板](/help/analyze/analysis-workspace/templates/use-templates.md)。
> 
>自 2015 年发布 Analysis Workspace 以来，Reports &amp; Analytics 的功能已经转移到 Analysis Workspace，并且已经达到工作流程等同性的阈值。本通知解释了生命周期结束的过程。
>
>详细了解 Reports &amp; Analytics [生命周期结束公告](https://www.adobe.com/go/analytics_rnaeol_cn)。

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



## 归因模型 {#attribution-models-details}

当某个量度的回顾窗口内出现多个值时，归因模型决定了哪些维度项获得量度的点数。只有在回顾窗口中设置了多个维度项的情况下，归因模型才适用。如果只设置了一个维度项，无论使用哪种归因模型，该维度项都会获得 100% 的点数。

| 图标 | 归因模型 | 定义 |
| :---: | :--- | --- |
| ![最后接触](/help/assets/icons/AttributeLastTouch.svg) | 最后接触 | 100% 归因于转化前最近发生的接触点。对于未另行指定归因模型的任何量度，此归因模型通常是默认值。组织通常在转化时间相对较短的情况下使用此模型，例如用于分析内部搜索关键字。 |
| ![首次接触](/help/assets/icons/AttributeFirstTouch.svg) | 首次接触 | 将 100% 的点数分配给归因回顾窗口中首次看到的接触点。组织通常使用此模型来了解品牌意识或客户获取。 |
| ![线性](/help/assets/icons/AttributeLinear.svg) | 线性 | 将点数平分给促成转化的每个接触点。当转化周期较长或需要更频繁的客户参与时，这个模型就很有用。组织通常使用此归因模型来衡量移动应用程序通知的有效性或用于基于订阅的产品。 |
| ![参与率](/help/assets/icons/AttributeParticipation.svg) | 参与率 | 将 100% 的点数分给所有独特的接触点。由于每个接触点都获得 100% 的点数，因此量度数据加起来通常会超过 100%。如果某个维度项多次出现而促成了转化，就会删除重复的值，直至 100%。如果您想要了解客户接触最多的接触点，此归因模型是理想的选择。媒体组织通常使用此模型来计算内容速度。零售组织通常使用此模型来了解其网站的哪些部分对于转化至关重要。 |
| ![同一接触](/help/assets/icons/AttributeSameTouch.svg) | 同一接触 | 100% 归因于发生转化的同一个事件。如果接触点没有在相同的事件上发生转化，它就被归类为“无”。这种归因模型有时相当于根本没有归因模型。如果您不希望来自其他事件的值影响一个量度如何给维度项分配点数，这种模型就很有价值。产品或设计团队可以使用此模型来对发生转化的页面的有效性进行评估。 |
| ![U 型](/help/assets/icons/AttributeUShaped.svg) | U 型 | 将 40% 的点数分给首次交互，40% 的点数分给最后交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，这两个接触点各占 50% 的点数。这种归因模型最适合用于您最重视第一次和最后一次互动，同时又不想完全忽视这期间其他互动的情况。 |
| ![J 曲线](/help/assets/icons/AttributeJCurve.svg) | J 曲线 | 将 60% 的点数分给最后一次交互，20% 的点数分给首次交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，最后一次互动占 75% 的点数，首次互动占 25% 的点数。与 U 型类似，此归因模型倾向于第一次和最后一次互动，但更大程度上倾向于最后一次互动。 |
| ![反向 J](/help/assets/icons/AttributeInverseJ.svg) | 反向 J | 将 60% 的点数分给首次接触点，20% 的点数分给最后接触点，并将剩余 20% 的点数分给这两次接触点之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，第一次互动占 75% 的点数，最后一次互动占 25% 的点数。与 J 型类似，此归因模型倾向于第一次和最后一次互动，但更大程度上倾向于第一次互动。 |
| ![时间衰减](/help/assets/icons/AttributeTimeDecay.svg) | 时间衰减 | 采用具有自定义半衰期参数的指数衰减，默认值为 7 天。每个渠道的权重，取决于在接触点启动与最终转化之间流逝的时间。用于确定点数的公式是 `2^(-t/halflife)`，其中 `t` 是接触点与转化之间流逝的时间。然后，所有接触点均被标准化为 100%。非常适合您想要根据特定的重要事件衡量归因的情况。此事件后发生转化所需的时间越长，所占点数就越少。 |
| ![自定义](/help/assets/icons/AttributeCustom.svg) | 自定义 | 您可以指定要赋予“首次接触点”、“最后接触点”以及“这两次互动之间的任意接触点”的权重。即便输入的自定义数字相加之和并不等于 100，指定的值也会被标准化为 100%。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的交互，中间参数会被忽略。然后，首次接触点和最后接触点会被标准化为 100%，并相应地分配点数。此模型非常适合那些希望完全控制其归因模型，并具有其他归因模型不能满足的特定需求的分析者。 |
| ![算法](/help/assets/icons/AttributeAlgorithmic.svg) | 算法 | 使用统计技巧，动态确定所选量度的最佳点数分配。归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend 算法是对“沙普利值”解决方案（以诺贝尔经济学奖获得者罗伊德·沙普利 (Lloyd Shapley) 命名）的推广形式，用于为对结果具有不同贡献的各参与者分配功能值（点数）。<br>从一个较高的层面来看，归因通过参与者联盟的方法计算，剩余值必须公平地分配给这些参与者。每个联盟的剩余值分配都根据每个子联盟（或先前参与的维度项）先前产生的剩余值通过循环计算得出。有关更多详细信息，请参阅约翰·海萨尼 (John Harsanyi) 和罗伊德·沙普利（Lloyd Shapley）的原文：<br>Lloyd Shapley S. (1953)。A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## 归因容器 {#attribution-container}

归因容器定义所需的归因范围。 可能的选项包括：

* **访问**：查看访问容器范围内的转化。
* **访客**：查看访客容器范围内的转化。

## 归因回顾窗口 {#attribution-lookback-window}

回顾窗口是指转化应回顾以包含接触点所花费的时间。如果一个维度项设置在回顾窗口之外，该值就不包含在任何归因计算中。

* **14 天**：自转化发生后最多回顾 14 天。
* **30 天**：自转化发生后最多回顾 30 天。
* **60 天**：自转化发生后最多回顾 60 天。
* **90 天**：自转化发生后最多回顾 90 天。
* **自定义时间：**&#x200B;您可以设置一个转换发生后的自定义回顾窗口。您可以指定分钟数、小时数、天数、周数、月数或季度数。例如，如果转化发生在 2 月 20 日，五天回顾窗口就会在归因模型中评估从 2 月 15 日到 2 月 20 日的所有维度接触点。

## 归因举例   {#attribution-example}

请仔细研究下面的示例：

1. 9 月 15 日，某位访客通过付费搜索广告访问您的网站，然后离开。
1. 9 月 18 日，该访客通过朋友提供的社交媒体链接再次访问您的网站。他将多个物品添加到购物车，但没有购买任何物品。
1. 9 月 24 日，您的营销团队向他们发送一封电子邮件，其中包含购物车中某些物品的产品建议券。他应用了产品建议券，但访问了其他几个网站，查看是否有其他产品建议券可用。他通过展示广告找到另一个网站，并最终购买了价值 50 美元的物品。

根据您的归因模型，容器和渠道会获得不同的点数。 有关示例，请参阅下表：

| 模型 | 容器 | 回顾时间范围 | 说明 |
|---|---|---|---|
| 首次接触 | 访问 | 30 天 | 归因仅考虑第三次访问。 在电子邮件与展示广告之间，电子邮件是首次接触点，因此电子邮件在 50 美元的购买中获得 100% 的点数。 |
| 首次接触 | 访客 | 30 天 | 归因会考虑所有三次访问。 付费搜索是首次接触点，因此它在 50 美元的购买中获得 100% 的点数。 |
| 线性 | 访问 | 30 天 | 点数在电子邮件和展示广告之间分配。 这两个渠道各自获得贡献 25 美元的点数。 |
| 线性 | 访客 | 30 天 | 点数分为付费搜索、社交、电子邮件和展示广告。 每个渠道各自获得此次购买中贡献 12.50 美元的点数。 |
| J曲线 | 访客 | 30 天 | 点数分为付费搜索、社交、电子邮件和展示广告。<ul><li>将 60% 的点数分给展示广告，其贡献价值是 30 美元。</li><li>将 20% 的点数分给付费搜索，贡献价值是 10 美元。</li><li>剩余的 20% 点数分给社交和电子邮件，二者的贡献价值均为 5 美元。</li></ul> |
| 时间衰减 | 访客 | 30 天 | <ul><li>展示广告接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`</li><li>电子邮件接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`</li><li>社交媒体接触点与转化之间的间隔为 6 天。`2^(-6/7) = 0.552`</li><li>付费搜索接触点与转化之间的间隔为 9 天。`2^(-9/7) = 0.41`</li>将这些值标准化处理之后得到以下结果：<ul><li>展示广告：33.8%，贡献价值是 16.88 美元</li><li>电子邮件：33.8%，贡献价值是 16.88 美元</li><li>社交：18.6%，贡献价值是 9.32 美元</li><li>付费搜索：13.8%，贡献价值是 6.92 美元</li></ul></li></ul> |

如果点数归属于多个渠道，则通常具有整数个点数的转化事件会被拆分。例如，如果使用线性归因模型计算订单归因，并且两个渠道都对该订单有贡献，则这两个渠道将分别获得该订单 50% 的点数。这些部分量度会针对所有人进行汇总，然后四舍五入到最接近的整数以供报告。

## 历程可视化图表比较 {#journey-visualization-comparisons}

Customer Journey analytics 中的各种可视化图表旨在分析您为客户提供的各历程。

使用以下信息来选择最符合您需求的可视化图表。

| 功能 | 历程画布 | 流失 | 流量 |
|---------|----------|---------|---------|
| **页面预定义序列** | 是</br>预定义分析和探索性分析相结合。使用路径上的预定义节点时会使用最终路径（只要访客最终从一个预定义节点移动到另一个预定义节点，就会被计算在内）。也可以显示即时（非最终）的下一个节点。 | 是</br>路径可以是最终路径，也可以被限制到下一个接触点 | 否 |
| **页面探索序列（临时分析）** | 是</br>预定义分析和探索性分析相结合。使用路径上的预定义节点时会使用最终路径（只要访客最终从一个预定义节点移动到另一个预定义节点，就会被计算在内）。也可以显示即时（非最终）的下一个节点。 | 有限</br>您可以单击右键，在自由格式表中查看立即流失。 | 是</br>仅探索性分析。始终在节点之间的一个维度实例内。这意味着每个节点都显示路径上紧邻的（而非最终的）下一个接触点。 |
| **显示人们离开（流失）和继续通过（流过）的位置** | 是</br>显示预定义历程和探索历程 | 是</br>显示预定义历程 | 是</br>显示探索性历程 |
| **线性历程** | 是 | 是 | 否 |
| **具有多个入口点和路径的非线性历程** | 是 | 否 | 是 |
| **主要量度** | 任何量度，包括计算量度 | 仅会话或人员 | 仅发生次数（路径视图） |
| **辅助量度** | 是<p>任何量度，包括计算量度</p> | 否 | 否 |
| **节点或接触点中的组件支持** | 量度、维度项目、过滤器和日期范围。 | 量度、维度项目、过滤器和日期范围。 | 仅维度项（起始和结束接触点除外） |
| **比较筛选器** | 否 | 是<p>在同一份报告中，对两种不同的过滤器进行并排比较。</p> | 否 |
| **拖放组件互动** | 是 | 是 | 否 |
| **Adobe Journey Optimizer 历程** | 是</br>从Journey Optimizer打开历程以进行更深入的分析和自定义 | 否 | 否 |

{style="table-layout:auto"}



## 标记过滤器部分 {#tagfiltersection}

| 标记 | 描述 |
|---|---|
| ![标记](/help/assets/filter-tag.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 标记]**&#x200B;部分按标记进行过滤。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索标记*&#x200B;来搜索可以用于过滤的标记。</li><li>您可以选择多个标记。可用的标记取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(1)**：选定标记的数量（如果选择了一个或多个标记）。</li><li>**2︎⃣**：当前过滤器产生的项目可用的标记数量。</li><li>7︎⃣：与特定标记相关的项目数量。</li></ul></li></ul> |


## 报表包过滤器部分 {#reportsuitefiltersection}

| 报表包 | 描述 |
|---|---|
| ![重新发布套件](/help/assets/filter-reportsuite.png){width="300"} | 通过&#x200B;**[!UICONTROL 报表包]**&#x200B;部分，可筛选报表包。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索报表包*&#x200B;以搜索可用于过滤的报表包。</li><li>您可以选择多个报表包。 可用的报表包取决于在过滤器面板的其他部分中所做的选择。</li><li>这些数字表明：<ul><li>**(2)**：选定报表包的数量（如果选择了一个或多个报表包）。</li><li>**3︎⃣**：可用于当前筛选器生成的项目的报表包数。</li><li>⃣4︎：与特定报表包关联的项目数。</li></ul></li></ul> |

## 已启用状态过滤器部分 {#enabledstatusfiltersection}

| 已启用状态 | 描述 |
|---|---|
| ![已启用状态](/help/assets/filter-enabledstatus.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 已启用状态]**&#x200B;部分按已启用状态进行过滤。 <ul><li>您可以选择多个状态。</li><li>这些数字表明：<ul><li>**(2)**：选定状态的数量（如果选择了一个或多个状态）。</li><li>**2︎⃣**：当前过滤器产生的项目可用的状态数量。</li><li>1︎⃣：与特定状态相关的项目数量。</li></ul></li></ul> |

## 类型过滤器部分 {#typefiltersection}

| 类型 | 描述 |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 类型]**&#x200B;部分按类型进行过滤。 <ul><li>您可以选择多个类型。</li><li>这些数字表明：<ul><li>**(2)**：选定类型的数量（如果选择了一个或多个类型）。</li><li>**1︎⃣**：当前过滤器产生的项目可用的类型数量。</li><li>3︎⃣：与特定类型相关的项目数量。</li></ul></li></ul> |

## 所有者过滤器部分 {#ownerfiltersection}

| 所有者 | 描述 |
|---|---|
| ![所有者](/help/assets/filter-owners.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 所有者]**&#x200B;部分按所有者进行过滤。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索所有者*&#x200B;来搜索可以用于过滤的所有者。</li><li>您可以选择多个所有者。可用的所有者取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(2)**：选定所有者的数量（如果选择了一个或多个所有者）。</li><li>**3︎⃣**：当前过滤器产生的项目可用的所有者数量。</li><li>4︎⃣：与特定所有者相关的项目数量。</li></ul></li></ul> |

## 其他过滤器过滤器部分 {#otherfiltersfiltersection}

| 其他过滤器 | 描述 |
|---|---|
| ![其他过滤器](/help/assets/filter-other.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 其他过滤器]**&#x200B;部分按其他预定义过滤器进行过滤。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 显示所有]**</li><li>**[!UICONTROL 与我共享]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已批准]**</li><li>**[!UICONTROL 收藏夹]**</li></ul> 您可以选择的内容取决于您的角色和权限。</li><li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(1)**：选定其他过滤器的数量（如果选择了一个或多个其他过滤器）。</li><li>**5︎⃣**：当前过滤器产生的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定的其他过滤器相关的项目数量。</li></ul></li></ul> |

## 日期范围过滤器部分  {#daterangefiltersection}

| 应用的日期范围 | 描述 |
|---|---|
| ![日期范围](/help/assets/filter-daterange.png){width="300"} | 您可以使用应用的日期范围部分按适用于项目的日期范围进行过滤。<ol><li>选择日期范围。</li><li>在日程表弹出窗口中定义一个日期范围，或选择一个可用的预设。<br>或者，您也可以直接在过滤器面板的日期范围部分指定一个日期范围。</li></ol><ul><li>这些数字表明：<ul><li>**(1)**：对默认预设更改后已更改日期范围的数量。</li><li>**5︎⃣**：当前过滤器产生的项目可用的日期范围数量。</li></ul> |
