---
description: 对全局报表包的描述
title: 全局报表包
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
role: Admin
source-git-commit: 2f61febc3e19b4b8d57833204b987cb64a9b7467
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 95%

---

# 全局报表包

全局报表包从您的组织拥有的所有域和应用程序收集数据。它要求实施方式将所有图像请求都发送到单个报表包。

Adobe 建议在大多数情况下实施全局报表包。有关实施全局报表包的优点，请参阅[全局报表包注意事项](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=zh-Hans)。

可使用&#x200B;*多包标记*&#x200B;和&#x200B;*虚拟报表包*&#x200B;方法将贵公司全局报表包数据的子集提供给不同的最终用户。

* **多包标记**：通过多包标记，可将图像请求不仅发送到全局报表包，还可发送到个别的子报表包。在所有报表包上去除重复的全局报表数据。

  例如，您可能将所有数据收集到一个全局报表包中，还根据品牌、区域或另一区分因素设置辅助报表包。贵公司中的不同团队随后即可集中精力处理报表包中与其相关的数据。

  要使用多包标记，请实施子报表包以及一个含有子报表包中所有数据的全局报表包。您的网页和应用程序的跟踪代码将包括全局报表包的报表包 ID (RSID)，还将包括适用的子报表包的 RSID。<!-- Wording/be more specific? And include any links? -->

  对图像请求中的每个报表包进行单独的服务器调用。对子报表包的调用为辅助调用。

* **虚拟报表包**：[虚拟报表包](/help/components/vrs/vrs-about.md)是对收集到全局报表包中的指定区段的查询，并对指定的用户组可用。通过虚拟报表包，无需使用多包标记，即可为不同的最终用户编排报表元素，从而避免辅助服务器调用。

  要使用虚拟报表包，请实施一个全局报表包，然后解析数据以创建应用了特定区段并具有特定组权限的虚拟报表包。可在虚拟报表包管理器（[!UICONTROL “组件”]>[!UICONTROL “虚拟报表包”]）中创建虚拟报表包。有关详细信息，请参阅[虚拟报表包工作流程](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)。

使用虚拟报表包代替多包标记一般是最佳实践，但虚拟报表包有一些局限。请参阅[虚拟报表包和多包标记注意事项](/help/components/vrs/vrs-considerations.md)以确定何种报表包方法对于您的业务需求是最佳选择。有关虚拟报表包与多包标记功能的深入比较，请参阅[虚拟报表包与多包标记](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)。

<!---## Rollup reports

>[!NOTE]
>
>[!DNL Reports & Analytics] is the only tool that supported rollup reports. Reports & Analytics was end-of-lifed on January 17, 2024.

Limitations of Rollup Reports {#limitations-rollups}

* Rollups provide total data, but they do not report individual values in reports. For example, eVar1 values are not included, but their aggregate total can be.
* Data is not deduplicated when the rollup combines data across report suites.
* Rollups run nightly at midnight.
* When you add a report suite to an existing rollup, historical data is not included in the rollup.
* All child report suites must have data in them for a rollup to function. If new report suites are included in a rollup, make sure to send at least one page view to each of those report suites.
* Rollup report suites can include a maximum of 40 child report suites.
* Rollup report suites can include a maximum of 100 events.
* Data contained in rollup report suites does not support breakdowns or segments.
* The Pages report is replaced with the Most Popular Sites report, which reports on metrics at the child-suite level.

## Comparison of Global Report Suite and Rollup Report  Features

**Secondary server calls**: Rollups do not incur any additional server calls beyond what a single report suite collects. If your organization uses multi-suite tagging, secondary server calls are made for each additional report suite included in an image request.

>[!TIP]
>
>If you use only a global report suite with [virtual report suites](/help/components/vrs/vrs-considerations.md), no secondary server calls are needed.

**Implementation changes**: Rollups do not require any implementation changes, while global report suites require you to include the global report suite ID in your implementation.

**Duplication**: Global report suites deduplicate unique visitors, while rollups do not. For example, if a user visits three of your domains in the same day, rollups would count three daily unique visitors. Global report suites would record one unique visitor.

**Time frame**: Rollups are only processed at midnight each night, while global report suites report data with standard latency.

**Breadth**: Rollups have no way to communicate between report suites. Global report suites can attribute credit to conversion variables between report suites and provide pathing across report suites.

**Historical data**: Rollups can aggregate historical data, while global report suites only report data from the point they were implemented.

**Reports**: Global report suites provide data on all dimensions; rollups provide aggregate data on only high-level reports.

**Supported products**: Rollups could only be used in Reports & Analytics. They are not supported in Analysis Workspace, or Data Warehouse. Global report suites can be used across all products.

**Number of aggregated report suites**: Rollups only support a maximum of 40 child report suites. Global report suites can be implemented on any number of domains or apps that you own.--->
