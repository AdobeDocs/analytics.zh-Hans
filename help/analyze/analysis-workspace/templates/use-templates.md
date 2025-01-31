---
description: 有关如何在Analysis Workspace中使用模板的概述。
title: 使用模板
feature: Analysis Workspace
role: User, Admin
exl-id: 9e5d1b35-e2b3-4fa5-af12-67bb913675bc
source-git-commit: f39ca03cd87ff5584348c526646f3eb39dfa75fd
workflow-type: tm+mt
source-wordcount: '18672'
ht-degree: 83%

---

# 使用模板

Analysis Workspace中的模板（或公司模板）可快速分析最常见的报表方案。 以下是您可以使用模板回答的一些问题示例：

* 访问网站的人数
* 其中多少访客是独特访客（只算一次）
* 访问网站的途径（例如是通过链接访问还是直接访问）
* 访客搜索网站内容所使用的关键字
* 访客在特定页面或整个网站逗留的时间
* 访客单击了哪些链接，访客离开网站的时间
* 哪些营销渠道对产生收入或转化事件效果最好
* 他们观看视频花费多长时间
* 他们访问网站使用哪些浏览器和设备

以下信息介绍了如何从Analysis Workspace的[!UICONTROL 模板]选项卡访问和使用模板。

## 访问和运行模板

1. 在 Analysis Workspace 中，选择 [!UICONTROL **Workspace**] 选项卡。

   <!--update screenshot -->

   ![“报告”选项卡](assets/view-prebuilt-templates.png)

1. 在&#x200B;[!UICONTROL **模板**]&#x200B;部分中，选择以下任一选项卡：

   * **[!UICONTROL Adobe模板]**：显示Adobe提供的所有模板。

   * **[!UICONTROL _login_company_name _模板]**：显示已为您的组织创建的所有公司模板。

     只有管理员才能创建公司模板。 有关如何创建公司模板的详细信息，请参阅[创建和管理模板](/help/analyze/analysis-workspace/reports/create-company-reports.md)。

1. 使用以下任一选项可更改查看可用模板的方式：

   * 通过选择列视图![列视图图标](assets/column-view-icon.png)或卡片视图![卡片视图图标](assets/card-view-icon.png)图标，选择是在列视图还是卡片视图中查看模板。

   * 使用卡片视图![卡片视图图标](assets/card-view-icon.png)时，请从以下排序顺序中进行选择： **[!UICONTROL 最近使用]**、**[!UICONTROL 最受欢迎]**、**[!UICONTROL 按字母顺序]**、**[!UICONTROL 类别]**。

1. 在搜索字段中，开始键入要查找的模板的名称，然后从模板列表中选择该模板。 您还可以按prop、eVar和事件编号来搜索模板列表。<!-- still true? -->

   或

   选择要查看的模板类别，然后从模板列表中选择模板。

   >[!TIP]
   >
   >要使用箭头键导航菜单，请按正斜杠键 (/)，然后按向下箭头键。按Enter加载选定的模板。

   有关可用模板的列表，请参阅下面的[可用模板](#available-reports)部分。

## 基于模板创建项目 {#use-reports}

模板可能并不完全适合您的需求，但它可以让您接近模板。 在这些情况下，您可以使用模板作为起点，然后对其进行自定义以最符合您的特定目的。

如果在进行更改后离开模板，系统将提示您保存或放弃更改。 将更改保存到模板可将模板另存为新项目。

要自定义模板并将其另存为项目，请执行以下操作：

1. 在 Adobe Analytics 中，选择 [!UICONTROL **Workspace**] 选项卡。

1. 选择&#x200B;[!UICONTROL **模板**]&#x200B;选项卡。

1. 选择要查看的模板。 例如，在&#x200B;[!UICONTROL **最受欢迎**]&#x200B;下，选择&#x200B;[!UICONTROL **页面**]&#x200B;模板。

   ![页面报告](assets/pages-report.png)

1. Analysis Workspace中显示的“页面”模板显示了两个[可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（[条状图](/help/analyze/analysis-workspace/visualizations/bar.md)和[摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)）和一个[自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 使用的量度为“发生次数”。
1. 执行下列任一操作：

   * 查看模板。
   * 将一个或多个区段拖到顶部的“区段”放置区中。例如，拖动区段&#x200B;[!UICONTROL **移动客户**]&#x200B;并查看结果。
   * 转到右上方的日历来更改日期范围。
   * 添加维度细分、拖入其他量度，并且通常根据您的需求自定义模板。

1. （可选）通过选择&#x200B;[!UICONTROL **项目**] > [!UICONTROL **保存**]，将模板另存为项目。

   模板另存为新项目；它不会修改现有模板。 有关保存项目的详细信息，请参阅[保存项目](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)。

## 可用模板

要访问所有可用的预建模板，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **Workspace**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **模板**]&#x200B;选项卡。

   预建模板按类别组织。

   <!--add screenshot-->

1. 选择一个类别以查看其中的模板。

   以下部分对应于可用的类别，并提供了有关每个模板的信息。

   * [[！UICONTROL ](#most-popular)

   * [[！UICONTROL ](#engagement)

### 最受欢迎 {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="查看所有订单内购买的单位总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解单位销售额随着时间的推移如何增加或减少。您可以应用区段来了解哪些客户或地区购买的单位最多，以及这些单位销售额随时间的变化趋势。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的单位销售额来评估最近发起的营销活动的有效性。也可以比较假期期间的同比单位销售额。<br/>此模板使用“天”维度和“单位”量度。"

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="培训教程模板"
>abstract="了解常见的 Analysis Workspace 术语，以及构建首个分析的步骤。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="找出最受欢迎和最不受欢迎的页面。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的受众，以及他们最感兴趣的信息类型。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整页面元数据以提高浏览量较少的页面的可见性，或者花时间改进浏览量最多的页面的内容。<br/>此模板使用“页面”维度和“页面浏览量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="查看页面总浏览量。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 "
>abstract="**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。<br/>此模板使用“天”维度和“页面浏览量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="查看总访问次数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。<br/>此模板使用“天”维度和“访问次数”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="查看独特访客的总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 "
>abstract="**这可以帮助您**&#x200B;更好地了解您网站的覆盖面和受众规模随着时间的推移或与前一时期相比是如何增加或减少的。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如，通过比较启动营销活动前后的独特访客数量来评估最近发起的营销活动是否成功吸引了新用户访问网站。或者您可以比较一下假期期间访问该网站的人数与去年同期相比的情况。<br/>此模板使用“天”维度和“独特访客量”量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="查看并排显示页面浏览量、访问量和独特访客量度的报告。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;比较这些重要的量度，以更全面地了解访问网站的独特人员数量、页面访问次数以及会话次数。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估每个人在特定一周或一个月内访问网站时查看的平均页面数，以及在一年中的某些时间或开展营销活动前后这些页面数的变化情况。<br/>此模板使用“天”维度、“页面浏览量”量度、“访问量”量度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="查看您网站上最受欢迎或表现最好的部分。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站中哪些部分的访问量最多。<br>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估您提供的哪些产品或服务最能引起人们的兴趣。<br/>此模板使用“网站部分”维度和“访问次数”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="查看人们访问某个页面后最常去的地方。"
>abstract="**这可以帮助您**&#x200B;更好地了解用户访问某个页面后的行为。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估是否可以优化页面设计或布局，以将人们引导到更理想的页面，例如进行购买或留下评论的页面。<br/>此模板使用“页面”维度和“事件”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="查看人们访问某个页面前最常去的地方。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些页面为某个页面带来了最多的流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估未作为前一个页面出现的页面是否需要更突出的指向当前页面的链接。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="查看那些最成功地为您的网站带来流量的链接。"
>abstract="**这可以帮助您**&#x200B;更好地了解在访问您的网站时，哪些跟踪代码（以及与它们关联的链接）使用得最多。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您在网站中添加链接的策略。<br/>此模板使用“跟踪代码”维度和“访问次数”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="按产品查看订单数量。数据显示一段时期内的情况。"
>abstract="**这可以帮助您**&#x200B;了解哪些产品需求量最高或最低。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您的营销策略，以推广表现优异的产品，或者改进或停产表现不佳的产品。您还可以根据数据分析来调整产品库存。<br/>此模板使用“产品”维度和“订单”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="查看访客在参与期间（默认为 30 天）匹配的最新营销渠道。"
>abstract="**这可以帮助您**&#x200B;了解哪些营销渠道在将人们吸引到您的网站并最终促成转化方面最为有效。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为表现优异的渠道分配更多资源，或者为表现不佳的渠道减少资源分配。<br/>此模板使用“最近接触渠道”维度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="查看访客在参与期间（默认为 30 天）匹配的最新营销渠道的详细信息。"
>abstract="**这可以帮助您**&#x200B;不仅了解哪些营销渠道在吸引人们访问您的网站并实现转化方面最有效，还可以了解这些营销渠道的详细信息。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为表现优异的渠道分配更多资源，或者为表现不佳的渠道减少资源分配。<br/>此模板使用“最近接触渠道详细信息”维度和“独特访客量”量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="查看所有订单中已购买全部产品的货币金额。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;了解收入随着时间的推移如何增加或减少。您可以将此量度与任何维度组合，以了解哪些维度项目对收入做出了贡献。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据以前的趋势预测未来的收入。您还可以添加另一个维度，例如跟踪代码维度，以了解哪些营销活动产生的收入最多。<br/>此模板使用“天”维度和“收入”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="查看购买事件的总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解对您的产品和服务的兴趣是如何随着时间的推移而增加或减少的。您可以应用区段来了解哪些客户或地区下的订单最多，以及这些订单随时间的变化趋势。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的订单来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的订单。<br/>此模板使用“天”维度和“订单”量度。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **培训教程**] | 了解常用的Analysis Workspace术语和构建首个分析的步骤 |
| [!UICONTROL **页面**] | <!--duplicated in Engagement section--> 找出最受欢迎和最不受欢迎的页面。 <p>**这可以帮助您**&#x200B;更好地了解您的受众，以及他们最感兴趣的信息类型。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如调整页面元数据以提高查看次数较少的页面上的可见性，或者花时间改进查看次数最多的页面的内容。</p><p>此模板使用[页面维度](/help/components/dimensions/page.md)和[页面查看次数量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **页面查看次数**] | <!--duplicated in Engagement section--> 查看页面总浏览量。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[页面查看次数量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **访问次数**] | <!--duplicated in Engagement section--> 查看总访问次数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[访问次数量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **访客**] | <!--duplicated in Engagement section--> 查看独特访客的总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的覆盖面和受众规模随着时间的推移或与前一时期相比是如何增加或减少的。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如，通过比较启动营销活动前后的独特访客数量来评估最近发起的营销活动是否成功吸引了新用户访问网站。或者您可以比较一下假期期间访问该网站的人数与去年同期相比的情况。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **关键量度**] | <!--duplicated in Engagement section--> 查看并排显示页面浏览量、访问量和独特访客量度的报告。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;比较这些重要的量度，以更全面地了解访问网站的独特人员数量、页面访问次数以及会话次数。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如，评估每个人在给定的一周或一个月内访问网站时查看的平均页面数量，以及在一年中的特定时间或运行营销活动之前和之后该数量的变化情况。 </p><p>此模板使用[天维度](/help/components/dimensions/day.md)、[页面查看次数量度](/help/components/metrics/page-views.md)、[访问次数量度](/help/components/metrics/visits.md)和[独特访客次数量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **网站区域**] | 查看您网站上最受欢迎或表现最好的部分。 <p>**这可以帮助您**&#x200B;更好地了解您网站中哪些部分的访问量最多。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估您提供的哪些产品或服务最能引起人们的兴趣。</p> <p>此模板使用[网站区域维度](/help/components/dimensions/site-section.md)和[访问次数量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **跟踪代码**] | 查看那些最成功地为您的网站带来流量的链接。 <p>**这可以帮助您**&#x200B;更好地了解在访问您的网站时，哪些跟踪代码（以及与它们关联的链接）使用得最多。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您在网站中添加链接的策略。</p><p>此模板使用[跟踪代码维度](/help/components/dimensions/tracking-code.md)和[访问次数量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **下一页**] | 查看人们访问某个页面后最常去的地方。 <p>**这可以帮助您**&#x200B;更好地了解用户访问某个页面后的行为。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估是否可以优化页面设计或布局，以将人们引导到更理想的页面，例如进行购买或留下评论的页面。</p> <p>此模板使用页面维度和事件量度。</p> |
| [!UICONTROL **上一页**] | 查看人们访问某个页面前最常去的地方。 <p>**这可以帮助您**&#x200B;更好地了解哪些页面为某个页面带来了最多的流量。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估未作为前一个页面出现的页面是否需要更突出的指向当前页面的链接。</p><p>此模板使用页面维度和事件量度。</p> |
| [!UICONTROL **产品**] | 按产品查看订单数量。数据显示一段时期内的情况。 <p>**这可以帮助您**&#x200B;了解哪些产品需求量最高或最低。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您的营销策略，以推广表现优异的产品，或者改进或停产表现不佳的产品。您还可以根据数据分析来调整产品库存。</p><p>此模板使用[产品维度](/help/components/dimensions/product.md)和[订单量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **最近联系渠道**] | 查看访客在参与期间（默认为 30 天）匹配的最新营销渠道。<p>**这可以帮助您**&#x200B;了解哪些营销渠道在将人们吸引到您的网站并最终促成转化方面最为有效。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为表现优异的渠道分配更多资源，或者为表现不佳的渠道减少资源分配。</p><p>此模板使用[最近联系渠道维度](/help/components/dimensions/last-touch-channel.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **最近联系渠道详细信息**] | 查看访客在参与期间（默认为 30 天）匹配的最新营销渠道的详细信息。<p>**这可以帮助您**&#x200B;不仅了解哪些营销渠道在吸引人们访问您的网站并实现转化方面最有效，还可以了解这些营销渠道的详细信息。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为表现优异的渠道分配更多资源，或者为表现不佳的渠道减少资源分配。</p><p>此模板使用[最近联系渠道详细信息维度](/help/components/dimensions/last-touch-detail.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **收入**] | 查看所有订单中已购买全部产品的货币金额。数据显示了某段时间内的数据，并与之前的时间段进行了比较。<p>**这可以帮助您**&#x200B;了解收入随着时间的推移如何增加或减少。您可以将此量度与任何维度组合，以了解哪些维度项目对收入做出了贡献。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据以前的趋势预测未来的收入。您还可以添加另一个维度，例如跟踪代码维度，以了解哪些营销活动产生的收入最多。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[收入量度](/help/components/metrics/revenue.md)。</p> |
| [!UICONTROL **订单数**] | 查看购买事件的总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解对您的产品和服务的兴趣是如何随着时间的推移而增加或减少的。您可以应用区段来了解哪些客户或地区下的订单最多，以及这些订单随时间的变化趋势。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的订单来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的订单。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[订单量度](/help/components/metrics/orders.md)。</p> |
| [!UICONTROL **件数**] | 查看所有订单内购买的单位总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解单位销售额随着时间的推移如何增加或减少。您可以应用区段来了解哪些客户或地区购买的单位最多，以及这些单位销售额随时间的变化趋势。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的单位销售额来评估最近发起的营销活动的有效性。也可以比较假期期间的同比单位销售额。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[单位量度](/help/components/metrics/units.md)。</p> |

### 参与 {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="查看当前正在您的网站上收集的维度和量度。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站上的流行趋势。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如回应和积极管理当前营销内容和活动的效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="查看访客每次访问时在您的网站所逗留的平均时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。<br/>此模板使用“天”维度和“每次访问的逗留时间（秒）”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="查看用户在成功事件之前所逗留的平均时间。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客执行所需操作（例如购买）所需的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对网站的更改是否能提高访客快速达成某个成功事件的能力。<br/>此模板使用“发生事件之前逗留的时间”维度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="查看访客在哪些页面离开或继续浏览预定义的页面序列。"
>abstract="**这可以帮助您**&#x200B;更好地了解用户是在历程中的哪些地方流失的。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过您网站上的特定流程（如购买或注册流程）分析转化率，或者分析您网站上各事件之间的关联。（例如，查看过隐私政策的用户中有多大比例会继续购买产品。）您还可以使用此模板在同一报告中对两个不同区段进行并排比较。<br/>此模板使用了“流失”可视化图表。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="查看人们在历程的各个阶段使用的设备。"
>abstract="**这可以帮助您**&#x200B;更好地了解有多少人与您的品牌互动、他们使用的设备类型，以及他们使用多种设备对体验的影响。例如，出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面？用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？依此类推。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化用户历程的某些部分以获得移动体验。<br/>此模板使用“流量”可视化图表、“流失”可视化图表、“同类群组”分析、“人员”量度和“独特设备”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="查看谁是您的忠实用户以及他们都在您的网站上做些什么。"
>abstract="**这可以帮助您**&#x200B;更好地了解平均每个人访问网站的次数、再次访问网站的频率以及两次访问之间的间隔天数。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容最能有效地吸引人们回到网站。<br/>此模板使用“访问次数”量度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="查看所有数字设备上的媒体音频消费的趋势和热门量度。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客如何在您的网站上使用音频内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容被使用得最多。<br/>此模板使用“访问次数”量度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="查看所有数字设备上的媒体消费的趋势和热门量度。"
>abstract="**这可以帮助您**&#x200B;更好地了解平均每个人访问网站的次数、再次访问网站的频率以及两次访问之间的间隔天数。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容最能有效地吸引人们回到网站。<br/>此模板使用“访问次数”量度和“独特访客量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="查看重新加载过程中维度项目的出现次数。访客刷新其浏览器是触发重新载入的最常见方式。"
>abstract="**这可以帮助您**&#x200B;识别某个页面何时可能出现问题，提示访客重新加载页面。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估哪些页面存在需要解决的问题。<br/>此模板使用“重新加载次数”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="查看访客每次访问时在您的网站所逗留的平均时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。<br/>此模板使用“天”维度和“每次访问的逗留时间（秒）”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="查看访客在存留期首次访问您的网站时访问的热门页面。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些页面为您的网站带来了最多的流量，或者更多地了解访客对您网站的第一印象。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化人们在网站上获得的初步体验，或者确保人们在进入您的网站时首先看到的页面是友好的，并提供指向您网站其他区域的必要链接。<br/>此模板使用“会话”量度。它还使用了条形可视化内容和自由格式表可视化内容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="查看单个唯一页面的访问次数。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。<br/>此模板使用“单页面访问量”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="查看 Adobe Experience Manager 网站的性能数据。"
>abstract="**这可以帮助您**&#x200B;更好地了解 Adobe Experience Manager 的价值实现。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化您的 Experience Manager 设置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="查看您的 Adobe Experience Manager Forms 的性能数据。"
>abstract="**这可以帮助您**&#x200B;更好地了解 Adobe Experience Manager 的价值实现。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化您的 Experience Manager 设置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="查看并分析智能防跟踪 (ITP) 对数据收集和报告的影响。"
>abstract="**这可以帮助您**&#x200B;更好地了解由于 ITP 实行的 Cookie 限制而造成的潜在数据丢失。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您的分析设置以最大限度地减少 ITP 的影响。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="查看访客每次访问您的网站时平均花费的时间，以及用户在成功事件发生前平均花费的时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客参与度，以及访客执行所需操作（例如购买）所需的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对网站的更改是否能提高访客快速达成某个成功事件的能力。<br/>此模板使用“天”维度和“每次访问所花费的时间（秒）”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="查看哪些网络内容的使用量最高，并且最能吸引用户。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们首次进入网站时会去哪里、人们最常访问网站的哪些部分，以及哪些页面最有可能让人们离开网站。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估网站上的哪些路径会引导人们访问最重要的页面，以及哪些页面最有可能让人们离开网站。<br/>此模板使用“页面”维度和“页面浏览量”量度、“访问量”量度、“独特访客量”量度、“进入率”量度、“跳出率”量度、“退出率”量度和“内容速度”量度。它还使用 Flow 可视化内容来表示进入、离开和热门部分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="查看哪些媒体内容的使用量最高，并且最能吸引用户。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们首次进入网站时会去哪里、人们最常访问网站的哪些部分，以及哪些页面最有可能让人们离开网站。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估网站上的哪些路径会引导人们访问最重要的页面，以及哪些页面最有可能让人们离开网站。<br/>此模板使用“页面”维度和“页面浏览量”量度、“访问量”量度、“独特访客量”量度、“进入率”量度、“跳出率”量度、“退出率”量度和“内容速度”量度。它还使用 Flow 可视化内容来表示进入、离开和热门部分；使用 Satterplot 可视化内容来显示最常见页面的页面浏览量；使用 Bar 可视化内容来显示按时间段划分的页面浏览量；使用 Line 可视化内容来显示在网站上花费的平均时间的趋势视图。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="查看人们在访问某个地方后或即将访问某个地方前，通常会去的地方。"
>abstract="**这可以帮助您**&#x200B;了解流量如何从给定页面流向您网站的其他部分，并了解人们到达给定页面所采用的路径。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估是否可以优化页面设计或布局，以将人们引导到更理想的页面，例如进行购买或留下评论的页面。或者评估当前页面上的信息是否可能为从之前的页面来到这里的人们提供他们所寻找的方向或操作。或者，您可以评估那些没有像之前页面那样显示的页面，是否需要更显眼的链接来指向当前页面。<br/>此模板使用“下一项或上一项”面板。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="查看您所有资产中任何页面的关键信息。显示页面浏览量、趋势线、流量可视化等。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们如何与给定页面进行交互。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，比如分析页面在一段时间内的性能，或者更好地理解是什么推动了页面流量的增长。<br/>此模板使用“页面浏览量”量度。它还使用 Line 可视化和 Flow 可视化。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="查看人们首次访问您的网站时访问的热门页面。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些页面为您的网站带来了最多的流量，或者更多地了解访客对您网站的第一印象。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化人们在网站上获得的初步体验，或者确保人们在进入您的网站时首先看到的页面是友好的，并提供指向您网站其他区域的必要链接。<br/>此模板使用“会话”量度。它还使用了条形可视化内容和自由格式表可视化内容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="查看人们在即将离开您的网站之前访问的热门页面。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些页面会导致人们离开网站。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新常见的退出页面，以优化人们在离开前获得的体验，或者包含内容或链接，以鼓励人们留在您的网站上。<br/>此模板使用“会话”量度。它还使用了条形可视化内容和自由格式表可视化内容。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **关键量度**] | <!--duplicated in Most popular section--> 查看并排显示页面浏览量、访问量和独特访客量度的报告。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;比较这些重要的量度，以更全面地了解访问网站的独特人员数量、页面访问次数以及会话次数。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如，评估每个人在给定的一周或一个月内访问网站时查看的平均页面数量，以及在一年中的特定时间或运行营销活动之前和之后该数量的变化情况。 </p><p>此模板使用[天维度](/help/components/dimensions/day.md)、[页面查看次数量度](/help/components/metrics/page-views.md)、[访问次数量度](/help/components/metrics/visits.md)和[独特访客次数量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **页面查看次数**] | <!--duplicated in Most popular section-->查看页面总浏览量。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[页面查看次数量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **页面**] | <!--duplicated in Most popular section-->找出最受欢迎和最不受欢迎的页面。 <p>**这可以帮助您**&#x200B;更好地了解您的受众，以及他们最感兴趣的信息类型。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如调整页面元数据以提高查看次数较少的页面上的可见性，或者花时间改进查看次数最多的页面的内容。</p><p>此模板使用[页面维度](/help/components/dimensions/page.md)和[页面查看次数量度](/help/components/metrics/page-views.md)。</p> |
| [!UICONTROL **访问次数**] | <!--duplicated in Most popular section-->查看总访问次数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的流量随着时间的推移如何增加或减少。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的网站流量来评估最近发起的营销活动的有效性。或者您可以比较一下同比假期期间的流量。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[访问次数量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **访客**] | <!--duplicated in Most popular section-->查看独特访客的总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解您网站的覆盖面和受众规模随着时间的推移或与前一时期相比是如何增加或减少的。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如，通过比较启动营销活动前后的独特访客数量来评估最近发起的营销活动是否成功吸引了新用户访问网站。或者您可以比较一下假期期间访问该网站的人数与去年同期相比的情况。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **每次访问逗留时间**] | 查看访客每次访问时在您的网站所逗留的平均时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[每次访问逗留时间（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| [!UICONTROL **发生事件之前逗留的时间**] | 查看用户在成功事件之前所逗留的平均时间。 <p>**这可以帮助您**&#x200B;更好地了解访客执行所需操作（例如购买）所需的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对网站的更改是否能提高访客快速达成某个成功事件的能力。</p><p>此模板使用[事件之前时间](/help/components/dimensions/time-prior-to-event.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **网站区域**] | <!--duplicated in Most popular section-->查看您网站上最受欢迎或表现最好的部分。 <p>**这可以帮助您**&#x200B;更好地了解您网站中哪些部分的访问量最多。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估您提供的哪些产品或服务最能引起人们的兴趣。</p> <p>此模板使用[网站区域维度](/help/components/dimensions/site-section.md)和[访问次数量度](/help/components/metrics/visits.md)。</p> |
| [!UICONTROL **实时**] | 查看当前正在您的网站上收集的维度和量度。 <p>**这可以帮助您**&#x200B;更好地了解您网站上的流行趋势。</p><p>**根据您了解的情况，您可能**&#x200B;响应并主动管理当前营销内容和营销活动的效果。</p> <p>此模板使用[实时报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。</p> |
| [!UICONTROL **Web内容使用**] | 查看哪些网络内容的使用量最高，并且最能吸引用户。<p>**这可以帮助您**&#x200B;更好地了解人们首次进入网站时会去哪里、人们最常访问网站的哪些部分，以及哪些页面最有可能让人们离开网站。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估网站上的哪些路径会引导人们访问最重要的页面，以及哪些页面最有可能让人们离开网站。</p> <p>此模板使用[页面维度](/help/components/dimensions/page.md)和[页面查看次数量度](/help/components/metrics/page-views.md)、[访问次数量度](/help/components/metrics/visits.md)、[独特访客数量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)和[内容周转率量度](/help/components/metrics/content-velocity.md)。 它还对登入、退出和顶部区域使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。</p> |
| [!UICONTROL **媒体内容使用**] | 查看哪些媒体内容的使用量最高，并且最能吸引用户。<p>**这可以帮助您**&#x200B;更好地了解人们首次进入网站时会去哪里、人们最常访问网站的哪些部分，以及哪些页面最有可能让人们离开网站。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估网站上的哪些路径会引导人们访问最重要的页面，以及哪些页面最有可能让人们离开网站。</p> <p>此模板使用[页面维度](/help/components/dimensions/page.md)和[页面查看次数量度](/help/components/metrics/page-views.md)、[访问次数量度](/help/components/metrics/visits.md)、[独特访客数量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)和[内容周转率量度](/help/components/metrics/content-velocity.md)。 它还对登入、退出和顶部区域使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)；显示最常见页面的页面查看次数的[状态图可视化图表](/help/analyze/analysis-workspace/visualizations/scatterplot.md)；显示按分段时间划分的页面查看次数的[条形图可视化图表](/help/analyze/analysis-workspace/visualizations/bar.md)；显示网站平均逗留时间的趋势视图的[折线图可视化图表](/help/analyze/analysis-workspace/visualizations/line.md)。</p> |
| [!UICONTROL **下一页和上一页流量**] | 查看访客在访问特定位置之前或之后最常前往的位置。<p>**这可以帮助您**&#x200B;更好地了解用户第一次进入网站时的去向、用户最常访问的网站区域，以及离开网站之前最有可能访问的页面。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估网站上的哪些路径会引导人们访问最重要的页面，以及哪些页面最有可能让人们离开网站。</p> <p>此模板使用[页面维度](/help/components/dimensions/page.md)和[页面查看次数量度](/help/components/metrics/page-views.md)、[访问次数量度](/help/components/metrics/visits.md)、[独特访客数量度](/help/components/metrics/unique-visitors.md)、[登入率量度](/help/components/metrics/entries.md)、[跳出率量度](/help/components/metrics/bounce-rate.md)、[退出率量度](/help/components/metrics/exits.md)和[内容周转率量度](/help/components/metrics/content-velocity.md)。 它还对登入、退出和顶部区域使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)；显示最常见页面的页面查看次数的[散点图可视化图表](/help/analyze/analysis-workspace/visualizations/scatterplot.md)；显示按分段时间划分的页面查看次数的[条形图可视化图表](/help/analyze/analysis-workspace/visualizations/bar.md)；显示网站平均逗留时间的趋势视图的[折线图可视化图表](/help/analyze/analysis-workspace/visualizations/line.md)。</p> |
| [!UICONTROL **流失**] | 查看访客在哪些页面离开或继续浏览预定义的页面序列。<p>**这可以帮助您**&#x200B;更好地了解用户是在历程中的哪些地方流失的。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过您网站上的特定流程（如购买或注册流程）分析转化率，或者分析您网站上各事件之间的关联。（例如，查看过隐私政策的用户中有多大比例会继续购买产品。）您还可以使用此模板在同一报告中对两个不同区段进行并排比较。</p> <p>此模板使用[流失可视化图表](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)。</p> |
| [!UICONTROL **跨设备分析**] | 查看人们在历程的各个阶段使用的设备。<p>**这可以帮助您**&#x200B;更好地了解有多少人与您的品牌互动、他们使用的设备类型，以及他们使用多种设备对体验的影响。例如，出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面？用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？依此类推。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化用户历程的某些部分以获得移动体验。</p> <p>此模板使用[流量可视化图表](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)、[流失可视化图表](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)、[同类群组分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)、[人员指标](/help/components/metrics/people.md)和[独特设备指标](/help/components/metrics/unique-devices.md)。</p> |
| [!UICONTROL **Web保留**] | 查看谁是您的忠实用户以及他们都在您的网站上做些什么。<p>**这可以帮助您**&#x200B;更好地了解平均每个人访问网站的次数、再次访问网站的频率以及两次访问之间的间隔天数。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容最能有效地吸引人们回到网站。<p>此模板使用[访问量度](/help/components/metrics/visits.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **流媒体使用**] | 查看所有数字设备上的媒体音频消费的趋势和热门量度。<p>**这可以帮助您**&#x200B;更好地了解访客如何在您的网站上使用音频内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容被使用得最多。<p>此模板使用[访问量度](/help/components/metrics/visits.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| [!UICONTROL **媒体回访间隔、频度、忠诚度**] | 查看所有数字设备上的媒体消费的趋势和热门量度。<p>**这可以帮助您**&#x200B;更好地了解平均每个人访问网站的次数、再次访问网站的频率以及两次访问之间的间隔天数。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如分析哪些内容最能有效地吸引人们回到网站。<p>此模板使用[访问量度](/help/components/metrics/visits.md)和[独特访客量度](/help/components/metrics/unique-visitors.md)。</p> |
| **[!UICONTROL 页面分析]** > [!UICONTROL **页面摘要**] | 查看访客每次访问时在您的网站所逗留的平均时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[每次访问逗留时间（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 页面分析]** > [!UICONTROL **重新加载**] | 查看重新加载过程中维度项目的出现次数。访客刷新其浏览器是触发重新载入的最常见方式。 <p>**这可以帮助您**&#x200B;识别某个页面何时可能出现问题，提示访客重新加载页面。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估哪些页面存在需要解决的问题。</p><p>此模板使用[重新加载指标](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/reloads)。</p> |
| **[!UICONTROL 页面分析]** > [!UICONTROL **页面逗留时间**] | 查看访客每次访问时在您的网站所逗留的平均时间。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[每次访问逗留时间（秒）量度](/help/components/metrics/time-spent-per-visit.md)。</p> |
| **[!UICONTROL 登录和退出]** > [!UICONTROL **登录页面**] | 查看用户在首次访问您的网站进行给定会话时访问的热门页面。 <p>**这可以帮助您**&#x200B;更好地了解哪些页面为您的网站带来了最多的流量，或者更多地了解访客对您网站的第一印象。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化人们在网站上获得的初步体验，或者确保人们在进入您的网站时首先看到的页面是友好的，并提供指向您网站其他区域的必要链接。</p><p>此模板使用“会话”量度。 它还使用了条形可视化内容和自由格式表可视化内容。</p> |
| **[!UICONTROL 登录和退出]** > [!UICONTROL **原始登录页面**] | 查看访客在存留期首次访问您的网站时访问的热门页面。 <p>**这可以帮助您**&#x200B;更好地了解哪些页面为您的网站带来了最多的流量，或者更多地了解访客对您网站的第一印象。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化人们在网站上获得的初步体验，或者确保人们在进入您的网站时首先看到的页面是友好的，并提供指向您网站其他区域的必要链接。</p><p>此模板使用“会话”量度。 它还使用了条形可视化内容和自由格式表可视化内容。</p> |
| **[!UICONTROL 进入和退出]** > [!UICONTROL **单页面访问次数**] | 查看单个唯一页面的访问次数。 <p>**这可以帮助您**&#x200B;更好地了解访客的参与度以及他们在网站上逗留的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估对您网站的更改是否会导致访客在网站上逗留更多时间。</p><p>此模板使用[单页面访问维度](https://experienceleague.adobe.com/en/docs/analytics/components/dimensions/single-page-visits)。</p> |
| **[!UICONTROL 进入和退出]** > [!UICONTROL **退出页面**] | 查看人们在即将离开您的网站之前访问的热门页面。<p>**这可以帮助您**&#x200B;更好地了解哪些页面正在将人们带离网站。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新常见的退出页面，以优化人们在离开前获得的体验，或者包含内容或链接，以鼓励人们留在您的网站上。</p><p>此模板使用“会话”量度。 它还使用了条形可视化内容和自由格式表可视化内容。</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **网站性能概述**] > [!UICONTROL **AEM网站性能**] | 查看 Adobe Experience Manager 网站的性能数据。  <p>**这可以帮助您**&#x200B;更好地了解 Adobe Experience Manager 的价值实现。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化您的 Experience Manager 设置。</p> |
| [!UICONTROL **Adobe Experience Manager**] > [!UICONTROL **表单性能概述**] > [!UICONTROL **AEM表单性能**] | 查看您的 Adobe Experience Manager Forms 的性能数据。  <p>**这可以帮助您**&#x200B;更好地了解 Adobe Experience Manager 的价值实现。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如优化您的 Experience Manager 设置。</p> |
| [!UICONTROL **ITP影响**] | 查看并分析智能防跟踪 (ITP) 对数据收集和报告的影响。 <p>**这可以帮助您**&#x200B;更好地了解由于 ITP 实行的 Cookie 限制而造成的潜在数据丢失。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整您的分析设置以最大限度地减少 ITP 的影响。</p> |

### 转化 {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="查看您网站上每个产品类别的访问次数。这对使用产品变量并希望查看产品类别相关量度的实施非常有用。如果网站上没有任何产品，则填充此模板的维度可能会特意留空。"
>abstract="**这可以帮助您**&#x200B;更好地了解最畅销或浏览量最高的产品。&lt;/br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如衡量特定产品营销活动的有效性。<br/>此模板使用“类别”维度和“访问次数”量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="查看关于您商业活动的零售商预建洞察以帮助您提高销量。虽然此功能面向 Adobe Commerce 的用户，但任何在线零售商均可使用。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的商业活动对销售额的贡献。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整各种活动的预算以获得最高 ROI。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="在显示购物车、结账和订单的漏斗可视化中查看产品转化情况。您还可以查看转化百分比、收入平均值、单位平均值和订单平均值。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们在转换过程中的进度和流失情况。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进您的网站以促进更顺畅的结账过程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="查看哪些产品表现最佳。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些产品最成功。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如增加对成功产品的资金投入，减少对不太成功产品的资金投入。<br/>此模板使用“产品浏览量”、“购物车添加量”、“订单量”、“收入”和“单位”量度。它还使用“产品”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="查看人们执行关键结账事件的次数，例如将商品添加到购物车、查看购物车、从购物车中移除商品以及结账。"
>abstract="**这可以帮助您**&#x200B;更好地了解结账流程中哪些环节有助于促成转化，哪些环节更容易导致购物车弃单。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如减少结账流程某些步骤中的摩擦。<br/>此模板使用"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="查看将产品添加到购物车的人数。"
>abstract="**这可以帮助您**&#x200B;更好地了解将产品添加到购物车的人数，而不是添加到购物车中的产品总数。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如衡量您的产品页面的有效性。<br/>此模板使用“购物车”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="查看人们查看购物车的次数。"
>abstract="**这可以帮助您**&#x200B;更好地了解结账体验，以降低购物车放弃率，或分析不同产品之间从加入购物车到结账之间的时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为在购物车中停留时间最长且最有可能被放弃的产品提供促销活动。<br/>此模板使用“购物车浏览量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="查看人们将商品添加到购物车的次数。"
>abstract="**这可以帮助您**&#x200B;更好地理解转化漏斗中客户对产品的兴趣达到足够高，以至于将其添加到购物车中的环节。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为所有客户改进产品推荐。例如分析哪些产品经常被添加到同一个购物车中，并根据购物车中已有的商品推荐相关产品。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="查看人们从购物车中移除商品的次数。"
>abstract="**这可以帮助您**&#x200B;更好地理解转化漏斗中客户对产品不再感兴趣的部分，或者帮助您了解结账流程中可能存在的问题。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如消除结帐过程中可能存在的任何潜在障碍，如复杂的用户体验。<br/>此模板使用“购物车移除量”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="在显示会话、购物车和订单的漏斗可视化中查看购买转化情况。您还可以查看转化百分比、收入平均值、单位平均值和订单平均值。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们在转换过程中的进度和流失情况。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进您的网站以促进更顺畅的结账过程。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **产品转化漏斗**] | 在显示购物车、结账和订单的漏斗可视化中查看产品转化情况。您还可以查看转化百分比、收入平均值、单位平均值和订单平均值。<p>**这可以帮助您**&#x200B;更好地了解人们在转换过程中的进度和流失情况。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进您的网站以促进更顺畅的结账过程。</p> |
| **产品** | 查看哪些产品可驱动关键量度，例如最畅销的产品或查看次数最多的产品。 <p>**这可以帮助您**&#x200B;更好地了解哪些产品最成功。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如增加对成功产品的资金投入，减少对不太成功产品的资金投入。</p><p>此模板使用订单量度和产品维度。 |
| **产品性能** | 查看哪些产品表现最佳。<p>**这可以帮助您**&#x200B;更好地了解哪些产品最成功。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如增加对成功产品的资金投入，减少对不太成功产品的资金投入。</p><p>此模板使用“产品查看”、“购物车添加”、“订单”、“收入”和“件数”量度。 它还使用“产品”维度。 |
| **类别** | 查看您网站上每个产品类别的访问次数。这对使用产品变量并希望查看产品类别相关量度的实施非常有用。如果网站上没有任何产品，则填充此模板的维度可能会特意留空。<p>**这有助于您**&#x200B;更好地了解最畅销或最常查看的产品。 </p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如衡量给定产品的营销活动有效性。</p><p>此模板使用类别维度和访问次数量度。 |
| **购物车转化漏斗** | 查看人们执行关键结账事件的次数，例如将商品添加到购物车、查看购物车、从购物车中移除商品以及结账。 <p>**这可以帮助您**&#x200B;更好地了解结账流程中哪些环节有助于促成转化，哪些环节更容易导致购物车弃单。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如减少结账流程某些步骤中的摩擦。</p><p>此模板使用 |
| **购物车** | 查看将产品添加到购物车的人数。<p>**这可以帮助您**&#x200B;更好地了解将产品添加到购物车的人数，而不是添加到购物车中的产品总数。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如衡量您的产品页面的有效性。</p><p>此模板使用购物车量度。 |
| **购物车查看** | 查看人们查看购物车的次数。 <p>**这可以帮助您**&#x200B;更好地了解结账体验，以降低购物车放弃率，或分析不同产品之间从加入购物车到结账之间的时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为在购物车中停留时间最长且最有可能被放弃的产品提供促销活动。</p><p>此模板使用购物车查看次数量度。 |
| **购物车加货** | 查看人们将商品添加到购物车的次数。 <p>**这可以帮助您**&#x200B;更好地理解转化漏斗中客户对产品的兴趣达到足够高，以至于将其添加到购物车中的环节。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为所有客户改进产品推荐。这可以通过分析哪些产品经常被添加到同一个购物车中，并根据购物车中已有的商品推荐相关产品来实现。 |
| **购物车减货** | 查看人们从购物车中移除商品的次数。<p>**这可以帮助您**&#x200B;更好地理解转化漏斗中客户对产品不再感兴趣的部分，或者帮助您了解结账流程中可能存在的问题。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如消除结帐过程中可能存在的任何潜在障碍，如复杂的用户体验。</p><p>此模板使用购物车减货量度。 |
| **购买转化漏斗** | 在显示会话、购物车和订单的漏斗可视化中查看购买转化情况。您还可以查看转化百分比、收入平均值、单位平均值和订单平均值。<p>**这可以帮助您**&#x200B;更好地了解人们在转换过程中的进度和流失情况。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进您的网站以促进更顺畅的结账过程。</p> |
| **收入** | <!--duplicated in Most popular section-->查看所有订单中购买产品的货币金额。<p>**通过将“收入”量度与任何维度组合，这可帮助您**&#x200B;更好地了解哪些维度项目对收入做出了贡献。 例如，您可以看到对收入贡献最大的热门促销活动（使用跟踪代码维度）。 </p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如调整未达到预期收入目标的促销活动。</p><p>此模板使用收入量度。 |
| **订单数** | <!--duplicated in Most popular section-->查看您的网站上发生的购买事件总数。 <p>**通过将“订单”量度与任何维度组合，这可以帮助您**&#x200B;更好地了解哪些维度项目对订单做出了贡献。 例如，您可以看到促成购买的热门促销活动（使用跟踪代码维度）。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如调整未达到预期购买目标的促销活动。 </p><p>此模板使用订单量度。 |
| [!UICONTROL **件数**] | 查看所有订单内购买的单位总数。数据显示了某段时间内的数据，并与之前的时间段进行了比较。 <p>**这可以帮助您**&#x200B;更好地了解单位销售额随着时间的推移如何增加或减少。您可以应用区段来了解哪些客户或地区购买的单位最多，以及这些单位销售额随时间的变化趋势。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过比较启动营销活动前后的单位销售额来评估最近发起的营销活动的有效性。也可以比较假期期间的同比单位销售额。</p><p>此模板使用[天维度](/help/components/dimensions/day.md)和[单位量度](/help/components/metrics/units.md)。</p> |
| [!UICONTROL **Magento：营销和商务**] | 查看关于您商业活动的零售商预建洞察以帮助您提高销量。虽然此功能面向 Adobe Commerce 的用户，但任何在线零售商均可使用。 <p>**这可以帮助您**&#x200B;更好地了解您的商业活动对销售额的贡献。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整各种活动的预算以获得最高 ROI。</p> |

### 受众 {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="查看与您的品牌互动的人数。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站的使用趋势。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如衡量最近的营销活动对吸引新访客到您网站的有效性。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="查看您网站上的页面查看次数和有关机器人流量的趋势。"
>abstract="**这可以帮助您**&#x200B;根据所配置的机器人规则更好地了解从报告中过滤掉的机器人流量数量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如继续监控机器人活动以识别新的模式。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="查看首次来访访客和重复访客的比较。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站在保留客户忠诚度方面的有效性，或者您获取新客户的速度。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如为首次来访访客提供未来购买的激励，以吸引他们回访。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="查看各个渠道中的个体用户行为。"
>abstract="**这可以帮助您**&#x200B;更好地了解完整的客户历程和跨多个接触点的互动。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如开展个性化营销，更好地针对用户偏好。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="查看访问您网站访客的热门时区。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客所处的时区。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整网站维护的时间，以尽量减少受影响的人数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="在地图可视化图表中查看访客位置的概述。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的访客所在的位置。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销资源集中在您认为最感兴趣和最有机会的地方。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="查看访问您网站访客的热门域名。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客来自哪些组织。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如以您最大的客户为目标提供内容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="查看访问您网站访客的热门域名。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客来自哪些组织。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如以您最大的客户为目标提供内容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="查看人们访问您网站时使用的热门浏览器宽度。"
>abstract="**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的浏览器宽度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。<br/>此模板使用“浏览器”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="查看人们访问您网站时使用的热门浏览器高度。"
>abstract="**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的浏览器高度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。<br/>此模板使用“浏览器”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="查看人们访问您网站时使用的操作系统名称和版本。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客最常使用的操作系统和版本。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门操作系统和版本测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="查看人们访问您网站时使用的操作系统名称。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客最常使用的操作系统。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门操作系统测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。<br/>此模板使用“移动运营商”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。<br/>此模板使用“移动运营商”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="查看访客访问过该网站的次数。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客返回网站时的参与度如何。这适用于访客的存留期，而不管项目日期范围如何。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对常客调整营销活动。<br/>此模板使用“访问编号”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="查看以前曾在您的网站上进行过 0 次购买、1 次购买、2 次购买、3 次购买或更多次购买的访客数量。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的网站如何影响购买行为。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如重点关注返回购买的访客，以便鼓励新访客的类似行为。<br/>此模板使用“客户忠诚度”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="查看访客从首次访问网站到购买之间的间隔天数。例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于 “1 天”维度项目。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客完成购买所需的间隔时间。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新您的网站以促进客户获取的速度。<br/>此模板使用“首次购买间隔天数”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="查看访客当前点击与最近一次购买之间的时间间隔。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客在网站上购物后的行为。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新您的网站以促进后续购买。<br/>此模板使用“上次购买间隔天数”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="查看人们访问您网站时使用的热门移动设备屏幕尺寸。"
>abstract="**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕尺寸测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="查看人们访问您网站时使用的热门移动设备屏幕高度。"
>abstract="**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕高度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="查看人们访问您网站时使用的热门移动设备屏幕宽度。"
>abstract="**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕宽度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="查看访问该网站的人员来自哪个国家或地区。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些国家或地区。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦在这些国家的营销努力，或者确保您的网站体验在主要语言不同的国家中达到最优。<br/>此模板使用“国家或地区”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="查看访问该网站的人员来自美国的哪个州。这与“地理区域”模板类似，但仅适用于美国。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自美国的哪些州。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦这些州的营销工作。<br/>此模板使用“美国州”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="查看访问该网站的人员来自哪个地理区域。区域是比国家小但比城市大的地理区域。在某些国家，地区是一个州、省或专区。在其他地区，它是一个成员国、辖区或大都市地区。 "
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些地区。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦在这些地区的营销努力，或者确保您的网站体验在主要语言不同的地区中达到最优。<br/>该模板使用“ID”（变量/地理国家）和“区域”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="查看访问该网站的人员来自哪个城市。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些城市。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦这些城市的营销工作。<br/>此模板使用“城市”维度"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="查看访问该网站的用户来自美国的哪些指定营销区域 (DMA)。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些地区。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦最成功的区域的营销工作。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="查看访客更倾向于查看内容的首选语言。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客最常用的语言。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如集中针对最流行的语言开展本地化工作或营销工作。<br/>此模板使用“语言”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="查看与人们访问您的网站所使用的技术相关的信息，例如操作系统、浏览器和设备。"
>abstract="**这可以帮助您**&#x200B;更好地了解访问您的网站时最常使用哪些技术。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对正在使用的技术优化您的网站。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="查看人们访问您网站时使用最多的浏览器的名称和版本。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客使用最多的浏览器。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门浏览器测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。<br/>此模板使用“浏览器”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="查看那些开发了人们用来访问您网站的最常用浏览器的组织名称。这与“浏览器”模板不同，因为它不会将同一浏览器的不同版本作为单独的维度项列出。"
>abstract="**这可以帮助您**&#x200B;更好地了解访客使用的最常见浏览器&#x200B;<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门浏览器测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。<br/>此模板使用“浏览器类型”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="查看移动应用程序上与每个屏幕相关的事件、会话和人数。"
>abstract="**这可以帮助您**&#x200B;更好地了解您网站中哪些屏幕最受欢迎。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进最受欢迎的屏幕上的内容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="查看人们在您的移动应用程序上采取的操作。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们如何使用您的应用程序以及他们从中获得的价值。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如对最受欢迎的功能进行补充或改进。"

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="查看应用程序的用户数、启动次数、首次启动次数以及平均会话时长。"
>abstract="**这可以帮助您**&#x200B;更好地了解应用程序的使用情况。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如提高应用程序性能，使其能够根据使用量进行扩展。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="查看移动设备应用程序的突出使用模式。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们如何使用应用程序。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进用户从一个屏幕进入另一个屏幕的方式，以最常见的工作流为目标。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="查看一些最常见的移动设备应用程序量度。"
>abstract="**这可以帮助您**&#x200B;更好地了解移动设备应用程序的基本性能。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估应用程序的整体健康状况和性能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="查看应用程序内消息传递和推送消息的性能数据。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们如何使用应用程序内消息传递功能，以及推送通知如何有效地为您的应用程序带来流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改善应用程序内消息推送通知体验。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="查看应用程序的运行情况以及用户遇到的问题。"
>abstract="**这可以帮助您**&#x200B;更好地了解使用应用程序的人是否遇到了运行缓慢或性能下降的情况。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如修复现有问题或在问题出现之前提高应用程序性能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="查看哪些用户是应用程序最忠诚的用户，以及他们在应用程序内都做些什么。"
>abstract="**这可以帮助您**&#x200B;更好地了解最忠诚的用户是如何使用您的应用程序的。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最忠诚的用户正在使用的功能改进您的营销工作。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **人员指标**] | 查看与您的品牌互动的人数。 <p>**这可以帮助您**&#x200B;更好地了解您网站的使用趋势。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如衡量最近的营销活动对吸引新访客到您网站的有效性。</p> |
| **访客资料** > **位置概述** | 在地图可视化图表中查看访客位置的概述。<p>**这可以帮助您**&#x200B;更好地了解访问您网站的访客所在的位置。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销资源集中在您认为最感兴趣和最有机会的地方。</p><!-- This template uses the --> |
| **访客资料** > **地域划分** > **地域国家/地区** | 查看访问该网站的人员来自哪个国家或地区。<p>**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些国家或地区。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦在这些国家的营销努力，或者确保您的网站体验在主要语言不同的国家中达到最优。</p><p>此模板使用国家/地区维度。 </p> |
| **访客个人资料** > **地域划分** > **美国地域州** | 查看访问该网站的人员来自美国的哪个州。这与“地理区域”模板类似，但仅适用于美国。<p>**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自美国的哪些州。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦这些州的营销工作。</p><p>此模板使用美国州维度。 </p> |
| **访客资料** > **地域划分** > **地域区域** | 查看访问该网站的人员来自哪个地理区域。区域是比国家小但比城市大的地理区域。在某些国家，地区是一个州、省或专区。在其他地区，它是一个成员国、辖区或大都市地区。 <p>**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些地区。</p><p>**根据您所学到的内容，您可能**&#x200B;会执行任意数量的操作，例如，使用数据来集中在这些地区的营销工作，或确保您的网站体验在具有不同主要语言的地区是最佳的。 </p><p>此模板使用ID（变量/地理国家/地区）和区域维度。 </p> |
| **访客个人资料** > **地域划分** > **地域城市** | 查看访问该网站的人员来自哪个城市。 <p>**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些城市。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如，使用这些数据集中在这些城市的营销工作。 </p><p>此模板使用城市维度。 </p> |
| **访客资料** > **地域划分** > **美国地域DMA** | 查看访问该网站的用户来自美国的哪些指定营销区域 (DMA)。<p>**这可以帮助您**&#x200B;更好地了解访问您网站的用户主要来自哪些地区。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如利用这些数据来聚焦最成功的区域的营销工作。 </p><!-- This template uses the --> |
| **访客资料** > **语言** | 查看访客更倾向于查看内容的首选语言。 <p>**这可以帮助您**&#x200B;更好地了解访客最常用的语言。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如集中针对最流行的语言开展本地化工作或营销工作。</p><p>此模板使用语言维度。</p> |
| **访客资料** > **时区** | 查看访问您网站访客的热门时区。 <p>**这可以帮助您**&#x200B;更好地了解访客所处的时区。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如调整网站维护的时间，以尽量减少受影响的人数。</p> |
| **访客资料** > **域** | 查看访问您网站访客的热门域名。 <p>**这可以帮助您**&#x200B;更好地了解访客来自哪些组织。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如以您最大的客户为目标提供内容。</p> |
| **访客资料** > **顶级域** | 查看访问您网站的访客的顶级域。 <p>**这可以帮助您**&#x200B;更好地了解访客来自哪些组织。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如以您最大的客户为目标提供内容。</p> |
| **访客资料** > **技术** > **技术概述** | 查看与用户用于访问网站的技术（如操作系统、浏览器和设备）相关的信息。 <p>**这可以帮助您**&#x200B;更好地了解访问您的网站时最常使用哪些技术。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如针对使用的技术优化您的网站。</p> |
| **访客资料** > **技术** > **浏览器** | 查看人们访问您网站时使用最多的浏览器的名称和版本。<p>**这可以帮助您**&#x200B;更好地了解访客使用最多的浏览器。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门浏览器测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p><p>此模板使用浏览器维度。 </p> |
| **访客资料** > **技术** > **浏览器类型** | 查看那些开发了人们用来访问您网站的最常用浏览器的组织名称。这与“浏览器”模板不同，因为它不会将同一浏览器的不同版本作为单独的维度项列出。<p>**这有助于您**&#x200B;更好地了解访客最常使用的浏览器</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门浏览器测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。 </p><p>此模板使用浏览器类型维度。 </p> |
| **访客资料** > **技术** > **浏览器宽度** | 查看人们访问您网站时使用的热门浏览器宽度。<p>**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的浏览器宽度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p><p>此模板使用浏览器维度。 </p> |
| **访客资料** > **技术** > **浏览器高度** | 查看用户用于访问您的网站的最高级别的浏览器。<p>**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的浏览器高度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p><p>此模板使用浏览器维度。 </p> |
| **访客资料** > **技术** > **操作系统** | 查看人们访问您网站时使用的操作系统名称和版本。<p>**这可以帮助您**&#x200B;更好地了解访客最常使用的操作系统和版本。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门操作系统和版本测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p> |
| **访客资料** > **技术** > **操作系统类型** | 查看人们访问您网站时使用的操作系统名称。<p>**这可以帮助您**&#x200B;更好地了解访客最常使用的操作系统。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用热门操作系统测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p> |
| **访客资料** > **技术** > [!UICONTROL **移动运营商**] | 查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用“移动设备运营商”维度。</p> |
| **访客维系** > **返回频率** | 查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用“移动设备运营商”维度。</p> |
| **访客维系** > **回访** | 查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用“移动设备运营商”维度。</p> |
| **访客维系** > **访问量** | 查看访客访问过该网站的次数。<p>**这可以帮助您**&#x200B;更好地了解访客返回网站时的参与度如何。这适用于访客的存留期，而不管项目日期范围如何。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对常客调整营销活动。</p><p>此模板使用访问数量维度。</p> |
| **访客维系** > **销售周期** > **客户忠诚度** | 查看以前曾在您的网站上进行过 0 次购买、1 次购买、2 次购买、3 次购买或更多次购买的访客数量。 <p>**这可以帮助您**&#x200B;更好地了解您的网站如何影响购买行为。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如重点关注返回购买的访客，以便鼓励新访客的类似行为。</p><p>此模板使用客户忠诚度维度。</p> |
| **访客维系** > **销售周期** > **首次购买前的天数** | 查看访客从首次访问网站到购买之间的间隔天数。例如，如果访客在首次访问后间隔一天购买商品，则任何后续访问或事件都属于“1 天”维度项目。<p>**这可以帮助您**&#x200B;更好地了解访客完成购买所需的间隔时间。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新您的网站以促进客户获取的速度。</p><p>此模板使用首次购买间隔天数维度。</p> |
| **访客维系** > **销售周期** > **自上次购买以来的天数** | 查看访客当前点击与最近一次购买之间的时间间隔。<p>**这可以帮助您**&#x200B;更好地了解访客在网站上购物后的行为。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如更新您的网站以促进后续购买。</p><p>此模板使用上次购买间隔天数维度。</p> |
| **移动设备** > **设备** | 查看人们用来访问您网站的移动设备的品牌和型号。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动设备有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最常见的移动设备优化您网站的呈现效果。</p><p>此模板使用移动设备名称维度。</p> |
| **移动设备** > **设备类型** | 查看人们用来访问您网站的移动设备类型，例如手机和平板电脑。<p>**这可以帮助您**&#x200B;更好地了解用于访问您网站的各种移动设备。</p><p>**根据您所了解的情况，您可以**&#x200B;执行任意数量的操作，例如针对最常用的移动设备类型优化您的网站。</p><p>此模板使用移动设备类型维度。</p> |
| **移动设备** > **制造商** | 查看哪些制造商生产人们用来访问您网站的移动设备，例如 Apple 和 Samsung。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的制造商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同制造商的能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用移动设备制造商维度。</p> |
| **移动设备** > **屏幕大小** | 查看人们访问您网站时使用的热门移动设备屏幕尺寸。<p>**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕尺寸测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p> |
| **移动设备** > **屏幕高度** | 查看人们访问您网站时使用的热门移动设备屏幕高度。<p>**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕高度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p> |
| **移动设备** > **屏幕宽度** | 查看人们访问您网站时使用的热门移动设备屏幕宽度。<p>**这可以帮助您**&#x200B;更好地了解如何向访客显示网站内容。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如通过使用最常见的移动设备屏幕宽度测试网站的新版本来提高网站质量。这样做可以最大限度地加强质量控制工作。</p> |
| **移动设备** > **移动应用程序使用情况** | 查看应用程序的用户数、启动次数、首次启动次数以及平均会话时长。<p>**这有助于您**&#x200B;更好地了解您的应用程序的使用量。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如提高应用程序性能，使其能够根据使用量进行扩展。</p><!-- This template uses the --> |
| **移动设备** > **移动应用程序历程** | 查看移动设备应用程序的突出使用模式。 <p>**这有助于您**&#x200B;更好地了解人们如何使用您的应用程序。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进用户从一个屏幕进入另一个屏幕的方式，以最常见的工作流为目标。 </p><!-- This template uses the --> |
| **移动设备** > **移动应用程序量度** | 查看一些最常见的移动设备应用程序量度。 <p>**这可以帮助您**&#x200B;更好地了解移动设备应用程序的基本性能。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如评估应用程序的整体健康状况和性能。</p><!-- This template uses the --> |
| **移动设备** > **移动应用程序消息** | 查看应用程序内消息传递和推送消息的性能数据。<p>**这可以帮助您**&#x200B;更好地了解人们如何使用应用程序内消息传递功能，以及推送通知如何有效地为您的应用程序带来流量。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改善应用程序内消息推送通知体验。</p><!-- This template uses the --> |
| **移动设备** > **移动应用程序性能** | 查看应用程序的运行情况以及用户遇到的问题。 <p>**这可以帮助您**&#x200B;更好地了解使用您应用程序的用户遇到性能缓慢还是性能下降。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如修复现有问题或在问题出现之前提高应用程序性能。</p><!-- This template uses the --> |
| **移动** > **移动应用保留** | 查看哪些用户是应用程序最忠诚的用户，以及他们在应用程序内都做些什么。 <p>**这可以帮助您**&#x200B;更好地了解最忠诚的用户是如何使用您的应用程序的。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最忠诚的用户正在使用的功能改进您的营销工作。</p><!-- This template uses the --> |
| **机器人** | 查看您网站上的页面查看次数和有关机器人流量的趋势。 <p>**这可以帮助您**&#x200B;根据所配置的机器人规则更好地了解从报告中过滤掉的机器人流量数量。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，如继续监视机器人活动以识别新模式。</p><!-- This template uses the --> |

### 客户获取 {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="查看您的网站如何在移动设备上吸引访客。"
>abstract="**这可以帮助您**&#x200B;更好地了解促成客户获取的各种因素，如搜索关键词、反向链接域等。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的渠道上。<br/>此模板使用“跳出率”量度和“跳出次数”量度。它还使用“搜索引擎”维度、“搜索关键词”维度、“登入页面”维度、“反向链接域”维度、“跟踪代码”维度和“反向链接”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="并排查看所有 Google 和 Bing 付费搜索数据。"
>abstract="**这可以帮助您**&#x200B;更好地了解发送到您网站的流量以及客户是否发生转化。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如估算广告营销活动的成本效益。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="查看访客在搜索结果的哪一页点击进入了您的网站。例如，如果您的网站出现在搜索引擎的搜索结果的第二页，则此变量的维度项目是“搜索页面 2”。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的网页在搜索结果中的排名。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如改进您的 SEO 策略，确保您的内容出现在搜索结果的第一页上。"

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="当使用自定义属性时，此模板显示访客如何到达您的网站。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些营销渠道最有效。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如加大对有效营销渠道的投入，并减少对效果不佳的营销渠道的投入。<br/>此模板使用“ID”（变量/营销渠道）维度和“收入”量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="查看访客在参与期间（默认为 30 天）首次匹配的营销渠道。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些营销渠道能给您的网站带来初始流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。<br/>此模板使用“首次接触渠道”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="查看访客在参与期间（默认为 30 天）首次匹配的营销渠道的详细信息。"
>abstract="**这可以帮助您**&#x200B;更好地理解是什么促成了与营销渠道相匹配的点击。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。<br/>此模板使用“首次接触渠道详细信息”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="查看您营销活动的点进次数和结账次数。"
>abstract="**这可以帮助您**&#x200B;更好地了解营销活动如何推动转化。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如确定哪些营销活动产生的 ROI 最高。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="查看有关您的营销活动效果的详细信息。"
>abstract="**这可以帮助您**&#x200B;更好地了解与营销活动相关的各种成功量度，例如收入、产品浏览量、订单量等。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在那些能带来最多收入的营销活动上。<br/>此模板使用“收入”量度、“产品浏览量”量度、“购物车添加量”量度、“订单量”量度和“单位”量度。它还使用“跟踪代码”维度和“反向链接域”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="查看您的网站是如何吸引访客的。"
>abstract="**这可以帮助您**&#x200B;更好地了解促成客户获取的各种因素，如搜索关键词、反向链接域等。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的渠道上。<br/>此模板使用“跳出率”量度和“跳出次数”量度。它还使用“搜索引擎”维度、“搜索关键词”维度、“登入页面”维度、“反向链接域”维度、“跟踪代码”维度和“反向链接”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="查看访客通过哪些搜索关键词找到您的网站，无论是付费搜索还是自然搜索。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如识别并填补正在使用的关键词与那些能推动网站流量的关键词之间的 SEO 差距。<br/>此模板使用“搜索关键词”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测相匹配。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如识别并填补正在使用的关键词与那些能推动网站流量的关键词之间的 SEO 差距。<br/>此模板使用“搜索关键词：付费”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测不匹配。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如识别并填补正在使用的关键词与那些能推动网站流量的关键词之间的 SEO 差距。<br/>此模板使用“搜索关键词：自然”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="查看访客通过哪些搜索引擎找到您的网站，无论是付费搜索还是自然搜索。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。<br/>此模板使用“搜索引擎”维度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="查看访客通过哪些搜索引擎进入您的网站，这些关键词与付费搜索检测相匹配。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。<br/>此模板使用“搜索引擎：付费”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测不匹配。"
>abstract="**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。<br/>此模板使用“搜索引擎：自然”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="查看人们通过哪些域名点击链接进入您的网站。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些第三方网站为您的网站带来最多的流量。（链接必须存在于外部网站上，且访客必须单击该链接才能显示维度项目。）<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如创建或调整内容，使其更符合来自热门反向链接域的访客的兴趣。<br/>此模板使用“反向链接域”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="查看人们点击进入您网站的第一个反向链接域。（设置后，它在该访客 ID 的整个生命周期内包含相同的值。）"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些第三方网站最初为您的网站带来了流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如创建或调整内容，以更好地迎合来自热门原始反向链接域的访客的兴趣。<br/>此模板使用“原始反向链接域”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="查看访客在点击链接进入您的网站时，之前浏览过的 URL。（链接必须存在于外部 URL 上，且访客必须单击该链接才能显示维度项目。）"
>abstract="**这可以帮助您**&#x200B;更好地了解哪些特定的 URL 为您的网站带来了最多的流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如创建或调整内容，以更好地迎合来自热门 URL 的访客的兴趣。<br/>此模板使用“反向链接域”维度。</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="查看访客是通过哪些通用渠道点击链接来到您的网站的。Adobe 维护每个渠道的规则。可能的渠道包括搜索引擎、社交网络、其他网站、硬盘或电子邮件。"
>abstract="**这可以帮助您**&#x200B;更好地了解哪种类型的反向链接能为您的网站带来最多的流量。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如创建或调整内容，以更好地迎合来自特定渠道的访客的兴趣。<br/>此模板使用“反向链接类型”维度。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **营销渠道**] > [!UICONTROL **渠道概述报告**] | 当使用自定义属性时，此模板显示访客如何到达您的网站。<p>**这可以帮助您**&#x200B;更好地了解哪些营销渠道最有效。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如加大对有效营销渠道的投入，并减少对效果不佳的营销渠道的投入。</p><p>此模板使用ID（变量/营销渠道）维度和收入量度。</p> |
| [!UICONTROL **营销渠道**] > [!UICONTROL **首次联系渠道**] | 查看访客在参与期间（默认为 30 天）首次匹配的营销渠道。 <p>**这可以帮助您**&#x200B;更好地了解哪些营销渠道能给您的网站带来初始流量。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。</p><p>此模板使用首次接触渠道维度。</p> |
| [!UICONTROL **营销渠道**] > [!UICONTROL **首次联系渠道详细信息**] | 查看访客在参与期间（默认为 30 天）首次匹配的营销渠道的详细信息。<p>**这可以帮助您**&#x200B;更好地理解是什么促成了与营销渠道相匹配的点击。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。</p><p>此模板使用首次接触渠道详细信息维度。</p> |
| [!UICONTROL **营销渠道**] > [!UICONTROL **最近联系渠道**] | 查看访客在该访客的参与期（默认为30天）内与之匹配的最新营销渠道。<p>**这有助于您**&#x200B;更好地了解哪些营销渠道给您的网站带来了流量，从而导致转化。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。</p><p>此模板使用“最近联系渠道”维度。  </p> |
| [!UICONTROL **营销渠道**] > [!UICONTROL **最近联系渠道详细信息**] | 查看有关访客在该访客的参与期（默认为30天）内与之匹配的最新营销渠道的详细信息<p>**这可以帮助您**&#x200B;更好地理解是什么促成了与营销渠道相匹配的点击。例如，如果访客到达您的网站且与“付费搜索”营销渠道匹配，则您可以使用渠道详细信息来查看使用了哪个搜索引擎或搜索了哪个关键词。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的领域。 </p><p>此模板使用“最近联系渠道详细信息”维度。 </p> |
| [!UICONTROL **促销活动**] > [!UICONTROL **促销活动转化漏斗**] | 查看您营销活动的点进次数和结账次数。 <p>**这可以帮助您**&#x200B;更好地了解营销活动如何推动转化。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如确定哪些营销活动产生的 ROI 最高。</p> |
| [!UICONTROL **促销活动**] > [!UICONTROL **促销活动效果**] | 查看有关您的营销活动效果的详细信息。<p>**这可以帮助您**&#x200B;更好地了解与营销活动相关的各种成功量度，例如收入、产品浏览量、订单量等。</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如，将营销工作重点放在带来最多收入的营销活动中。 </p><p>此模板使用收入量度、产品查看量度、购物车添加量度、订单量度和件数量度。 它还使用“跟踪代码”维度和“反向链接域”维度。 </p> |
| [!UICONTROL **促销活动**] > [!UICONTROL **跟踪代码**] | 查看您网站上的跟踪代码的名称。 您可以将具有不同查询字符串参数值的链接放在Internet的不同位置。<p>**这有助于您**&#x200B;更好地了解哪些链接最能成功吸引流量进入您的网站。 附加跟踪代码查询字符串在电子邮件、广告、社交媒体帖子以及您的组织使用的其他营销工作中很常见</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如，将营销工作重点放在带来最多收入的营销活动中。</p><p>此模板使用跟踪代码维度。 </p> |
| **Web 客户获取** | 查看您的网站是如何吸引访客的。<p>**这可以帮助您**&#x200B;更好地了解促成客户获取的各种因素，如搜索关键词、反向链接域等。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的渠道上。</p><p>此模板使用“跳出率”量度和“跳出次数”量度。 它还使用“搜索引擎”维度、“搜索关键词”维度、“登入页面”维度、“反向链接域”维度、“跟踪代码”维度和“反向链接”维度。  </p> |
| **移动客户获取** | 查看您的网站如何在移动设备上获取访客。<p>**这可以帮助您**&#x200B;更好地了解促成客户获取的各种因素，如搜索关键词、反向链接域等。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将营销重点放在最有效的渠道上。</p><p>此模板使用“跳出率”量度和“跳出次数”量度。 它还使用“搜索引擎”维度、“搜索关键词”维度、“登入页面”维度、“反向链接域”维度、“跟踪代码”维度和“反向链接”维度。  </p> |
| **Advertising Analytics：付费搜索** | 并排查看所有 Google 和 Bing 付费搜索数据。 <p>**这可以帮助您**&#x200B;更好地了解发送到您网站的流量以及客户是否发生转化。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如估算广告营销活动的成本效益。</p> |
| **搜索关键字 — 全部** | 查看访客通过哪些搜索关键词找到您的网站，无论是付费搜索还是自然搜索。 <p>**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。 </p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如识别并填补所使用的关键字与增加网站流量的关键字之间的SEO差距。</p><p>此模板使用“搜索关键字”维度。 </p> |
| **搜索关键词 — 付费** | 查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测相匹配。<p>**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如识别并填补所使用的关键字与增加网站流量的关键字之间的SEO差距。 </p><p>此模板使用“搜索关键字 — 付费”维度。 </p> |
| **搜索关键字 — 免费** | 查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测不匹配。<p>**这可以帮助您**&#x200B;更好地了解人们在搜索中使用的带来网站流量的关键词。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如识别并填补所使用的关键字与增加网站流量的关键字之间的SEO差距。</p><p>此模板使用“搜索关键字 — 免费”维度。 </p> |
| **搜索引擎 — 全部** | 查看访客通过哪些搜索引擎找到您的网站，无论是付费搜索还是自然搜索。 <p>**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。 </p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。</p><p>此模板使用搜索引擎维度。 </p> |
| **搜索引擎 — 付费** | 查看访客通过哪些搜索引擎进入您的网站，这些关键词与付费搜索检测相匹配。<p>**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。 </p><p>此模板使用搜索引擎 — 付费维度。 </p> |
| **搜索引擎 — 免费** | 查看访客通过哪些搜索关键词进入您的网站，这些关键词与付费搜索检测不匹配。<p>**这可以帮助您**&#x200B;更好地了解人们使用的带来网站流量的搜索引擎。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如将 SEO 工作的重点放在那些能为网站带来最多流量的搜索引擎上。</p><p>此模板使用“搜索引擎 — 免费”维度。 </p> |
| **所有搜索页面排名** | 查看访客在搜索结果的哪一页点击进入了您的网站。例如，如果您的网站出现在搜索引擎的搜索结果的第二页，则此变量的维度项目是“搜索页面 2”。<p>**这可以帮助您**&#x200B;更好地了解您的网页在搜索结果中的排名。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如改进您的SEO策略以确保您的内容显示在搜索结果的第一页。 </p> |
| **反向链接域** | 查看人们通过哪些域名点击链接进入您的网站。<p>**这可以帮助您**&#x200B;更好地了解哪些第三方网站为您的网站带来最多的流量。（链接必须存在于外部网站上，且访客必须单击该链接才能显示维度项目。）</p><p>**根据您了解的情况，您可能**&#x200B;会执行任意数量的操作，例如创建或调整内容，以更紧密地关注来自顶级反向链接域的访客的兴趣。 </p><p>此模板使用反向链接域维度。 </p> |
| **原始反向链接域** | 查看人们点击进入您网站的第一个反向链接域。（设置后，它在该访客 ID 的整个生命周期内包含相同的值。）<p>**这可以帮助您**&#x200B;更好地了解哪些第三方网站最初为您的网站带来了流量。</p><p>**根据您了解的情况，您可以**&#x200B;执行任意数量的操作，例如创建或调整内容，以更紧密地关注来自顶级原始反向链接域的访客的兴趣。 </p><p>此模板使用原始反向链接域维度。 </p> |
| **反向链接** | 查看访客在点击链接进入您的网站时，之前浏览过的 URL。（链接必须存在于外部 URL 上，且访客必须单击该链接才能显示维度项目。）  <p>**这可以帮助您**&#x200B;更好地了解哪些特定的 URL 为您的网站带来了最多的流量。</p><p>**根据您了解的情况，您可能**&#x200B;执行任意数量的操作，例如创建或调整内容，以更紧密地关注来自顶级URL的访客的兴趣。 </p><p>此模板使用反向链接域维度 </p><p>此模板使用反向链接维度。 </p> |
| **反向链接类型** | 查看访客是通过哪些通用渠道点击链接来到您的网站的。Adobe 维护每个渠道的规则。可能的渠道包括搜索引擎、社交网络、其他网站、硬盘或电子邮件。<p>**这可以帮助您**&#x200B;更好地了解哪种类型的反向链接能为您的网站带来最多的流量。</p><p>**根据您了解的情况，您可能**&#x200B;执行任意数量的操作，例如创建或调整内容，以使内容与来自特定渠道的访客的兴趣更紧密地保持一致。</p><p>此模板使用反向链接类型维度。</p> |

### 移动 {#mobile-not-ready-for-use}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。<br/>此模板使用“移动运营商”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="查看人们用来访问您网站的移动设备的品牌和型号。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动设备有哪些。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最常见的移动设备优化您网站的呈现效果。<br/>此模板使用“移动设备名称”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="查看人们用来访问您网站的移动设备类型，例如手机和平板电脑。"
>abstract="**这可以帮助您**&#x200B;更好地了解用于访问您网站的各种移动设备。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最常用的移动设备类型优化您的网站。<br/>此模板使用“移动设备类型”维度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="查看哪些制造商生产人们用来访问您网站的移动设备，例如 Apple 和 Samsung。"
>abstract="**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的制造商有哪些。<br/>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同制造商的能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。<br/>此模板使用“移动设备制造商”维度。"

<!-- markdownlint-enable MD034 -->

可以使用以下模板：

| 模板名称 | 为何使用此模板<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **移动运营商**] | 查看为人们访问您网站所使用的移动设备提供蜂窝网络连接的电信公司。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动运营商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同运营商的网络能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用“移动设备运营商”维度。</p> |
| **设备** | 查看人们用来访问您网站的移动设备的品牌和型号。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的移动设备有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最常见的移动设备优化您网站的呈现效果。</p><p>此模板使用移动设备名称维度。</p> |
| **设备类型** | 查看人们用来访问您网站的移动设备类型，例如手机和平板电脑。<p>**这可以帮助您**&#x200B;更好地了解用于访问您网站的各种移动设备。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如针对最常用的移动设备类型优化您的网站。</p><p>此模板使用移动设备类型维度。</p> |
| **制造商** | 查看哪些制造商生产人们用来访问您网站的移动设备，例如 Apple 和 Samsung。<p>**这可以帮助您**&#x200B;更好地了解您的用户群中最受欢迎的制造商有哪些。</p><p>**根据您所了解的情况，您可以**&#x200B;采取多种行动，例如根据不同制造商的能力来调整内容投放方式，以确保用户能够获得流畅的使用体验。</p><p>此模板使用移动设备制造商维度。</p> |
