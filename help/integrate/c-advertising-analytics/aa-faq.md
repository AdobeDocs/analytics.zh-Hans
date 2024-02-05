---
description: 围绕 Advertising Analytics 的常见问题。
title: Advertising analytics 常见问题解答
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 37%

---

# 常见问题解答

## 访问/权利 {#access}

+++ 是否需要成为Adobe Advertising Cloud或Adobe Advertising Cloud (AMO)客户才能访问此功能？

不需要，此功能适用于非Advertising Cloud和非AMO客户。 </p> <p>AMO 客户可以利用现有的 Analytics-AMO 集成；他们将无法使用 Ad Analytics。

+++

+++ 哪些Adobe Analytics SKU使您可以使用Advertising Analytics？

Advertising Analytics可用于Adobe Analytics

* [选择](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html)

+++

+++ 使用Advertising Analytics需要额外付费吗？

不需要，在适当的SKU配置之外，Advertising Analytics不会产生额外成本。

+++

+++ Advertising Analytics是否计入我的服务器调用使用情况

不会，Advertising Analytics使用特殊的数据源类型，不会产生服务器调用成本。

+++

+++ 如果我已经使用Advertising Cloud/AMO，还可以使用Advertising Analytics功能吗？

任何兼容的搜索引擎帐户都将传递到Advertising Analytics，并将以只读形式显示。 所有的编辑或更新都应在 Advertising Cloud/AMO 中处理。

+++

+++ 我拥有正确的SKU，但我无法访问Advertising Analytics，为什么？

Advertising Analytics仅适用于Adobe Analytics管理员；但是，管理员可以向非管理员授予访问权限。 请联系您的管理员获取访问权限。

+++

## 使用 Advertising Analytics {#using}

+++ Advertising Analytics中包含哪些搜索引擎帐户？

搜索引擎帐户包括Google AdWords和Microsoft Bing。

+++

+++ 我该从哪里访问Advertising Analytics？

登录到Adobe Analytics后，导航至 [!UICONTROL 管理员]. 然后选择 [!UICONTROL Advertising Analytics] 以添加您的搜索引擎帐户。

+++

+++ 如何收集数据并将其传递到Analytics？

Advertising Analytics利用一系列自定义API，通过Adobe Advertising Cloud将数据从搜索引擎传递到Analytics中。

+++

+++ 通过此集成，我可以获得哪些搜索数据？

你会得到

* 展示次数
* 点击量
* 成本
* 质量分数
* 直接来自搜索引擎的平均位置，以及
* AMO ID实例（单击实例）。

+++

+++ 我是否可以根据其他Advertising Analytics数据（指标/维度）划分我的Analytics数据？

不会，原始搜索数据将以独立数据集的形式提供。 不过，您可以通过其他 Analytics 数据对实例数版本的点击数据进行划分。

+++ 我的帐户的各种状态指示器（待处理、活动、已暂停等）的定义是什么？ 每个状态指标都标识每个搜索引擎帐户的生命周期阶段。

* [!UICONTROL 待处理]
* [!UICONTROL 暂停]表示该帐户之前进行过设置，但现在处于非活动状态。
* [!UICONTROL 活动]表示该帐户已完全设置并正在提取搜索数据。

+++

+++ 我正在尝试将我的Advertising Analytics帐户映射到特定的报表包，但该帐户在报表包模式中不可用。 为什么？

在将报表包分配到Advertising Analytics帐户之前，需要先执行以下操作 [已配置Advertising Analytics报表](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
此操作可通过单独的管理员页面完成，访问方式如下：管理员>报表包> [选择报表包] >编辑设置> Advertising Analytics配置。

+++

+++ 是否可以将虚拟报表包分配给Advertising Analytics帐户？

虚拟报表包不收集数据，因此您无法将Advertising Analytics帐户直接映射到虚拟报表包。 但是，您可以将Advertising Analytics帐户映射到您想要在其中查看数据的虚拟报表包的父报表包。 除非您根据AMO ID（或其分类）在区段逻辑中包含“或”条件，否则搜索引擎量度（点击次数/成本/展示次数）可能不会显示在虚拟报表包中。 示例：添加“存在 AMO ID 的所有点击”将包括该区段中的搜索引擎指标。

+++

+++ Advertising Analytics指标是否可在以下报告中报告： <b>营销渠道</b> 报告？

不可以，营销渠道报表中不包含这些指标。

+++

+++ 何时可将搜索数据提取到 Analytics 中？

您所在 Analytics 数据中心时区的上午 6 点 (06:00) 左右，系统会从搜索引擎中提取搜索数据。此时收集 AMO 数据并将其插入报表包。然后，在将数据插入 Analytics 的过程中，将该时间转换为报表包所在的时区。

+++

+++ 什么可以是 <b>在点击前捕获</b>？ 即使没有点击次数，我们是否也会捕获展示次数、成本、平均位置等数据？ </p> </td>

AMO ID将捕获以下搜索引擎指标：展示次数、成本、点击次数、平均位置和平均质量分数。 如果没有点击次数，但具有展示次数，则仍会将展示次数/位置/质量分数数据发送到 Analytics。一般情况下，如果没有点击次数，则也不会有成本。

+++

+++ 此数据是在哪个级别捕获的？ <b>访客？点击级别？</b>

搜索引擎量度是在点击级别捕获的，且关联到AMO ID（及其分类）。 此类数据是摘要级别的数据，未关联到访问次数/访客数。因此，搜索引擎指标只能在属于点击级别范围且基于 AMO ID（或其分类）的区段中使用。

AMO ID 也可以在登陆页面上通过点击该页面来捕获（这会将此 ID 关联到访问/访客），此 ID 将保留到下游，以便获取其他 Analytics 指标的点数（直到此 ID 过期或被新的 AMO ID 覆盖）。与任何其他 eVar 一样，AMO ID 会完全合并到数据集中。

+++

+++ 我们是只捕获google.com还是 <b>国家/地区版本</b> (例如google.co.uk、google.it、google.fr或google.de)？

广告平台分类可捕获以下值：“Google Adwords”和“Bing Ads”。 通常的最佳做法是将国家/地区代码包含在营销活动名称中。之后，您可以进一步过滤或分段（例如，如果所有促销活动均以 countrycode_ 开头，则创建一个以“UK_”开头的促销活动 (AMO ID) 区段，可提供仅与 UK 有关的数据）。

+++

+++ “AMO成本”量度是搜索引擎所报告的每个关键字/广告的成本花费。 这是指净成本还是总成本？

“AMO成本”只是支付给搜索引擎的成本。 它不包含任何代理费用或搜索优化/管理平台费用。

+++

+++ 是否有包括其他广告渠道的计划，例如 <b>显示</b> 或 <b>Social</b>？

否，目前我们在路线图中没有关于这些其他渠道的计划。

+++


## 自动跟踪与手动跟踪 {#section_7437C4698A6D482EB7ED94A948390119}

+++ 在设置我的广告帐户时，它声明<b> 自动跟踪</b> 可能导致意想不到的后果。 会产生什么样的后果？

自动模式会尝试以正确格式将URL参数附加到跟踪模板/目标URL的末尾。 <b>但是，您有责任确保添加的URL参数能够正确保持到最终登陆页面。 自动模式可以将关键字插入到登陆 URL 中，而您的 Web 服务器可能不支持包含特殊字符的关键字。

+++

+++ 如果我最初设置了手动或自动跟踪，那么我以后能否切换到另一种跟踪模式？ 会产生哪些影响？

可以，您可以切换跟踪模式，但在切换之前需要删除旧的跟踪逻辑。 这可能导致在切换当天出现一段跟踪停机时间（特别是从手动切换到自动时）。因此，我们建议不要切换，除非绝对必要。

* 从手动切换到自动：删除手动添加到跟踪模板的内容，然后在Advertising Analytics UI中将切换开关从手动切换到自动并保存设置。 请注意，系统可能需要几个小时才能填充自动跟踪代码。

* 从自动切换到手动：在Advertising Analytics设置UI中，将切换从手动更新为自动，然后尽可能快速地部署手动跟踪代码。 在部署手动跟踪代码时，如果您在搜索引擎跟踪模板中看到自动跟踪代码，请将其删除。

+++
