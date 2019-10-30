---
title: Cross-Device Analytics
description: 跨设备分析通过将设备数据拼接在一起，将您的数据从以设备为中心转变为以人为中心。
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Cross-Device Analytics

> [!NOTE] 随着功能的进一步开发，跨设备分析文档可能会发生更改。 定期回访以获取更新。

跨设备分析是一项功能，可将Analytics从以设备为中心的视图转变为以人为中心的视图。 此功能使用Adobe Experience Platform Identity service合作图或专用图来识别属于个人的设备，并将它们拼合在一起。 因此，分析师可以理解跨浏览器、设备或应用程序的用户行为。 通过使用 CDA，您可以回答类似下面的问题：

* 有多少人在与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的促销活动点进次数是否会导致转换到其他设备上？
* 如果考虑跨设备历程，我对促销活动效用的理解会有怎样的变化？我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？

当设备被拼接时，可变持久性会跨设备传递。 例如，用户首先通过桌面计算机上的广告访问您的网站。 该用户会找到您的移动应用程序，安装它，并最终在其移动设备上进行购买。 借助跨设备分析，收入可归因于他们在桌面计算机上单击的广告。

请参阅 [旅程IQ:跨设备分析Spark页](http://adobe.ly/aacda) ，进一步了解跨设备分析的功能和功能。

## 先决条件

自2019年9月起，跨设备分析需要满足以下条件。 与组织内的团队和Adobe客户经理合作，确保满足以下所有要求。

> [!IMPORTANT] 未能满足所有先决条件可能导致无法启用跨设备分析，或在拼接数据时结果不佳。

* 贵组织的数据必须位于Adobe的太平洋西北数据中心内。 计划为世界其他地区的数据中心提供支助。
* 请联系贵组织的客户经理以确定以下要点：
   * 必须与包含Adobe Analytics Ultimate的Adobe签订合同。
   * 贵组织必须使用Adobe Experience Platform Identity service合作图或专用图。 请参 [阅设备协作用户指南](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) 中的主页。
   * 贵组织必须同意允许Adobe在Microsoft azure服务器上处理和存储Analytics数据。 Adobe使用Azure存储设备图形数据并执行设备拼接。 因此，Adobe Analytics数据在Adobe的数据处理中心和Adobe在Microsoft Azure中的表现之间来回传递。
* 跨设备分析按每个报告包启用。 已启用CDA的报表包需要：
   * 报表包每天的点击量不能超过1亿。 这一门槛将在未来几个月中增加。
   * Adobe建议报表包包含跨设备数据，即来自多种设备类型（Web、应用程序等）的数据。 一些组织将此概念称为“全球”报表包，但CDA并非从地理角度严格来说必须是全球的。 跨设备分析不适用于多个报表包，也不能合并多个报表包的数据。
* 您的实施必须满足以下要求：
   * 必须部署最新版本的Experience Cloud ID服务。 请参阅 [Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html) Identity service用户指南中的主页。 大多数使用Adobe Experience Platform Launch的实施可能已部署ECID。
   * 只要可以 `setCustomerIDs` 识别个人身份（例如用户登录或打开电子邮件时），就调用该函数。 此要求适用于所有平台，包括使用时的移动应用程序。 请参 [阅](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) Experience Cloud Identity service用户指南中的setCustomerID。

## 限制

跨设备分析是一项突破性的、强大的功能，但其使用方式存在限制。

* CDA仅通过Analysis Workspace提供。
* 无法按照上述先决条件中所述跨报表包进行拼接。
* Adobe Analytics报表包不能映射到多个IMS组织。 由于CDA在给定的报表包内拼接设备，因此不能使用CDA跨多个IMS组织拼接数据。
* CDA当前与“客户属性”不兼容。 客户属性不能用于在跨设备区段内创建CDA虚拟报告套件，或用于在基于CDA虚拟报告套件的Analysis Workspace项目内进行报告。
* CDA需要合作图或专用图。 不支持第三方设备图形。
* 不支持旧版Analytics ID。 仅拼接具有Experience Cloud ID的访客。
* 客户服务部门尚未完全支持此功能。 跨 [设备分析论坛可用于支持此功能](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) ，包括Adobe产品经理的积极和直接参与。
* 跨设备分析使用虚拟报告套件和报告时间处理，它们有各自的限制。 有关这 [些限制的详细信息](../vrs/vrs-about.md) ，请参 [阅虚拟报告套件和报告时间处理](../vrs/vrs-report-time-processing.md) 。
* 访问网站的新设备最长可能需要两周时间才能通过合作图或专用图进行处理。 CDA中最近两周的缝合水平通常低于两周以前的日期范围。 Adobe计划改进Adobe Experience Platform Identity Service，以便将来实时拼接新设备。
* 虚拟报告套件中的历史数据会因Adobe识别和拼接设备而发生变化。 源报表包中的数据不会更改。

组织满足所有要求并了解其限制后，您便可以开始 [设置跨设备分析](cda-setup.md)。
