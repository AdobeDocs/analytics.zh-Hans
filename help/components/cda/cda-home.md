---
title: 跨设备分析
description: 跨设备分析通过拼接设备数据将数据从设备专注于专注于人的数据。
translation-type: tm+mt
source-git-commit: 47cde7b12b78e9394aac531d068634688c635ec1

---


# 跨设备分析

跨设备分析是一项功能，可将Analytics从以设备为中心的视图转变为以人为中心的视图。此功能使用Adobe Experience Platform Identity Service Co-op Graphic或Private Graph确定属于个人的设备，并将它们拼接在一起。因此，分析师可以了解跨越浏览器、设备或应用程序的用户行为。使用CDA，您可以回答诸如以下问题的问题：

* 有多少人与我的品牌互动？他们使用多少种设备？它们如何重叠？
* 人们在移动设备上开始任务的频率如何，然后后来移动到桌面PC以完成任务？在一台设备上登陆的营销活动点击是否会导致转换其他位置？
* 如果我考虑跨设备旅程，我如何理解营销活动有效性？我的漏斗分析如何改变？
* 用户从一台设备到另一台设备的最常用路径是什么？他们在哪里放弃？他们在何处取得成功？
* 具有多种设备的用户的行为如何与使用单个设备的用户不同？

拼接设备时，会跨设备执行可变持久性。例如，用户首先通过桌面计算机上的广告访问您的站点。该用户会查找您的移动应用程序，安装它，最后在其移动设备上进行购买。通过跨设备分析，收入可归因于他们在桌面计算机上点击的广告。

查看 [旅程IQ：跨设备分析Spark页面](http://adobe.ly/aacda) ，进一步了解跨设备分析的功能和功能。

## 先决条件

自2019年月起，跨设备分析需要以下各项。与组织内的团队及Adobe客户经理合作，确保您满足以下所有要求。

> [!IMPORTANT] 未能满足所有先决条件，可能导致在拼接数据时无法启用跨设备分析或不良结果。

* 贵组织的数据必须驻留在Adobe的太平洋西北数据中心内。计划在世界其他地区的数据中心支持。
* 请与贵组织的客户经理联系以建立以下要点：
   * 必须使用包含Adobe Analytics Ultimate的Adobe签署合同。
   * 您的组织必须使用Adobe Experience Platform Identity Service Co-op Graphic或Private Graph。请参阅 [Device](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) Co-op用户指南中的主页。
   * 贵组织必须同意允许Adobe在Microsoft Azure服务器上处理和存储Analytics数据。Adobe使用Azure存储设备图形数据并执行设备拼接。因此，Adobe Analytics数据在Adobe数据处理中心和Adobe在Microsoft Azure中的表现之间来回传递。
* 跨设备分析是在每个报告包上启用的。您的报表套件需要以下各项：
   * 此时，报告套件每天不能超过亿次点击量。此阈值将在未来几个月内增加。
   * “跨设备”报告套件，这意味着必须将跨设备的所有数据发送到同一个报告套件。一些组织将此称为“全局”报告套件，但CDA不严格必须是地理位置的全局。跨设备分析不能跨报表包工作。
* 您的实施必须满足以下要求：
   * 必须部署最新版本的Experience Cloud ID服务。请参阅Experience [Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html) Identity Service用户指南中的主页。大多数使用Adobe Experience Platform Launch的实施可能已经部署了EID。
   * 每当可以识别个人时调用 `setCustomerIDs` 该函数，如用户登录或打开电子邮件时。此要求适用于所有平台，包括移动应用程序(如果使用)。请参阅 [Experience Cloud Identity Service用户指南中](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) 的SetCustomerID。

## 限制

跨设备分析是一项突破性、强大的功能，但在如何使用它方面存在限制。

* CDA仅可通过Analysis Workspace获得。
* 在IMS组织中无法进行拼接。确保您未在实施中使用多个IMS Ocs。
* 如以上先决条件所述，不能跨报告套件进行拼接。
* CDA当前与客户属性不兼容。客户属性不能用于创建CDA虚拟报告套件、跨设备区段内的报告或在基于CDA虚拟报告套件的Analysis Workspace项目中报告。
* CDA需要计划图或私人图。不支持第三方设备图。
* 不支持传统Analytics ID。只有具有Experience Cloud ID的访客才会拼接。
* 客户关怀尚未完全支持此功能。[Cross-Device Analytics论坛](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) 可用于对此功能的支持，包括活动和直接从Adobe产品管理器进行的参与。
* 跨设备分析使用虚拟报告套件和报告时间处理，它们有自己的限制。有关这些限制的更多信息，请参阅 [虚拟报告套件](../vrs/vrs-about.md) 和 [报告时间处理](../vrs/vrs-report-time-processing.md) 。
* 访问您网站的新设备最长可能需要两周时间，由合作社图或私人图处理。CDA在最近两周内拼接的级别通常低于两周之前的日期范围。Adobe计划改进Adobe Experience Platform Identity Service以在未来实时缝合新设备。
* 虚拟报告套件中的历史数据会根据Adobe识别和拼接设备的情况进行更改。源报表包中的数据不会更改。

在您的组织满足所有要求并理解限制后，您可以开始 [设置跨设备分析](cda-setup.md)。
