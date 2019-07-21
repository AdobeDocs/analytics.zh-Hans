---
description: “单页面访问量”报表显示网站访客登入网站后直接退出的页面（即访客未进一步查看您网站上的任何其他页面），请不要将其与 Ad Hoc Analysis 中的“单页面访问量”量度混淆。
seo-description: “单页面访问量”报表显示网站访客登入网站后直接退出的页面（即访客未进一步查看您网站上的任何其他页面），请不要将其与 Ad Hoc Analysis 中的“单页面访问量”量度混淆。
seo-title: 单页面访问量
solution: Analytics
title: 单页面访问量
topic: 报表
uuid: 5ca52be8-c7 f5-464a-8a06-55e8271760 b4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 单页面访问量

“单页面访问量”报表显示网站访客登入网站后直接退出的页面（即访客未进一步查看您网站上的任何其他页面），请不要将其与 Ad Hoc Analysis 中的“单页面访问量”量度混淆。

此报表常用于[!UICONTROL 页面]报表，但是也可在所有启用了[!UICONTROL 路径分析]的流量变量中查看。您可以使用此报表来标识促使访客进一步浏览您网站的比例最小的登入页面，或者用于确定一个页面的单页访问量是多少。您可以根据此信息来优化页面内容，以减少这些页面的访客退出量。

## 报表的属性 {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* 通过提取[!UICONTROL 页面]报表并使用[!UICONTROL 单次存取]作为量度，可检索到相同的报表。

* 单页面访问指一次访问包含一个唯一值，而不是一次图像请求。

   * 在[页面报表](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5)中，在当次访问内只能触发一个唯一页面。
   * 在[网站区域报表](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD)中，在当次访问内会触发一个唯一网站区域。
   * 在[流量变量](/help/admin/admin/c-traffic-variables/traffic-var.md)中，如果触发了一个唯一值，则此报表中会填充一次访问。

* 如果报表中的变量包含一个唯一值，则单页面访问量可由许多图像请求组成。在填充了第二个唯一值之后，当次访问将不再被视为一次单页面访问。
* 这是一种路径分析报表。默认情况下，[!UICONTROL 页面]变量已启用路径分析。但是，任何流量变量都具备此功能。是否在其他流量变量上启用路径分析，取决于您的合同。请联系贵组织的客户经理以获得详细信息。
* 此报表可使用搜索过滤器来查找特定的行项目。
* 此报表可通过[趋势](/help/components/c-variables/dimensionslist/reports-types.md) 和 [排名](/help/components/c-variables/dimensionslist/reports-types.md) 格式。

* 此报表中没有可用的划分。
* 此报表内唯一可用的量度是[!UICONTROL “访问”]。

