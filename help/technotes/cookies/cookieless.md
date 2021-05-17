---
title: 减轻浏览器Cookie限制影响的选项
description: 了解如何减轻浏览器cookie限制的影响，以改进Adobe Analytics的数据收集。
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# 减轻浏览器Cookie限制影响的选项

本文档讨论在主要浏览器实施Cookie跟踪预防措施时跨属性和解决方案保留永久访客标识的选项。

Adobe Analytics依靠第一方Cookie记录访客的现场活动。 Analytics还依赖第三方Cookie来了解访客的场外活动，如您拥有的其他域的活动。 第三方Cookie在许多浏览器上被阻止，并且在Chrome即将取消的支持（目前计划2022年）下将基本不可用。 所有浏览器都允许使用第一方Cookie，但Apple的[ITP跟踪防范](https://webkit.org/tracking-prevention)措施下的Safari和其他浏览器的有效期有限。 有关浏览器cookie的当前限制的更多信息，请参阅[Adobe Analytics和浏览器cookie](cookies.md)。

这些浏览器限制反映了一种更广泛的趋势，即从匿名的第三方跟踪转向在用户和他们信任的品牌之间显式共享信息。 为支持此动作，Adobe为客户提供了通过包含通过其第一方关系收集的耐用标识符来补充传统cookie的方法。

## Customer Journey Analytics和跨设备分析

[Adobe客户](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) 历程分 [析和跨设](/help/components/cda/overview.md) 备分析使用户除了Cookie外，还可以包含持久标识符，如散列登录。这使您能够了解跨设备和跨线上和线下渠道的客户旅程(如果是Customer Journey Analytics):

* **客户历程** 分析功能以Adobe Experience Platform为构建基础，根据任何常见客户ID提供在Analysis Workspace中合并线上和线下数据的灵活性。您可以指定要用于任何给定分析的ID，并在Analysis Workspace中浏览数据。 Analytics Select、Prime和Ultimate客户有资格将其作为附加产品购买。

* **跨设备分** 析是对传统Adobe Analytics的增强，它允许客户将替代标识符用于访客。此功能可让您从以设备为中心的视图转变为以人为中心的视图。 Analytics Ultimate客户可使用跨设备分析。

## 服务器端数据收集

服务器端集合提供了提供您自己的标识符的灵活性，而不是依赖浏览器机制设置cookie。

您可以使用[数据插入API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md)或[批量数据插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)将数据提交到Analytics服务器端。 建议对新的服务器端实现使用批量数据插入API。 有关两个API的比较，请参阅“[我应使用哪个Adobe Analytics工具](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)”。

## 更多信息

有关您的企业可以采取的从第三方cookies中过渡的实际步骤，请参阅[通过Adobe](https://business.adobe.com/solutions/cookieless.html)和深入的[超越第三方cookie思考：没有第三方cookie的世界完整指南](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)。”

>[!MORELIKETHIS]
[Adobe Analytics 和浏览器 Cookie](cookies.md)>
>
