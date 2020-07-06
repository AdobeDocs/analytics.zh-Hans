---
title: 跨设备分析
description: 跨设备分析可将设备数据拼合在一起，从而将您的数据从以设备为中心转变为以人员为中心。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 96%

---


# 跨设备分析

跨设备分析是一项功能，可将 Analytics 从以设备为中心的视图转变为以人员为中心的视图。此功能使用 Adobe Experience Platform Identity Service 协作图或专用图来识别属于个人的设备，并将这些设备拼合在一起。因此，分析师可以了解跨浏览器、设备或应用程序的用户行为。通过使用 CDA，您可以回答类似下面的问题：

* 有多少人与我的品牌互动？ 他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的促销活动点进次数是否会导致转换到其他设备上？
* 如果考虑跨设备历程，我对促销活动效用的理解会有怎样的变化？我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？

当设备拼合在一起后，变量持久性会在设备之间传递。例如，用户首先通过台式计算机上的广告访问了您的网站。然后，该用户找到并安装了您的移动设备应用程序，而且最终在其移动设备上进行了购买。借助跨设备分析，收入可归因于他们在台式计算机上单击的广告。

请参阅[历程 IQ：跨设备分析 Spark 页面](http://adobe.ly/aacda)，了解关于跨设备分析功能和特征的详细信息。

## 先决条件

跨设备Analytics需要以下条件。 请与贵组织内的团队以及 Adobe 客户经理合作，确保满足以下所有条件。

>[!IMPORTANT]
>
> 如果不满足所有先决条件，则可能会导致无法启用跨设备分析，或者导致拼合数据时的结果不佳。

* 贵组织的数据必须位于 Adobe 的太平洋西北地区数据中心。我们计划将来为世界其他地区的数据中心提供支持。
* 联系贵组织的客户经理以确定以下要点：
   * 必须与 Adobe 签订有关 Adobe Analytics Ultimate 的合同。
   * 贵组织必须使用 Adobe Experience Platform Identity Service 协作图或专用图。请参阅《Device Co-op 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)。
   * 本着合作精神和透明精神，我们希望客户了解我们与跨设备分析相结合使用的 Microsoft Azure。Adobe 使用 Azure 存储设备图数据并执行跨设备拼合。因此，Adobe Analytics 数据在 Adobe 的数据处理中心和 Adobe 的 Microsoft Azure 预置实例之间来回传递。
* 跨设备分析是按报表包启用的。启用CDA的报表包需要：
   * 报表包中的每天点击量不能超过 5 亿次。
   * Adobe 建议在报表包中纳入跨设备数据，即，来自多种设备类型（Web、应用程序等）的数据。某些组织将此概念称为“全球”报表包，尽管从地理角度来说，CDA 并不一定包含严格意义上的全球范围。跨设备分析不适用于多个报表包，也无法合并多个报表包的数据。
* 您的实施必须满足以下要求：
   * 必须部署最新版本的 Experience Cloud ID 服务。请参阅《Experience Cloud Identity Service 用户指南》中的[主页](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。大多数使用 Adobe Experience Platform Launch 的实施可能已经部署 ECID。
   * 当个人身份可以识别（例如，用户登录或打开电子邮件）时，需调用 `setCustomerIDs` 函数。这项要求适用于所有平台，包括使用的移动设备应用程序。请参阅《Experience Cloud Identity Service 用户指南》中的 [setCustomerIDs](https://docs.adobe.com/content/help/zh-Hans/id-service/using/id-service-api/methods/setcustomerids.html)。

## 限制

跨设备分析是一项具有突破性的强大功能，但其使用方式存在限制。

* CDA 仅通过 Analysis Workspace 提供。
* 无法拼合多个报表包，如上述先决条件所述。
* Adobe Analytics 报表包无法映射到多个 IMS 组织。由于 CDA 拼合给定报表包内的设备，因此 CDA 无法用于拼合多个 IMS 组织之间的数据。
* CDA 当前与“客户属性”不兼容。“客户属性”无法用于在跨设备区段内创建 CDA 虚拟报表包，也无法用于基于 CDA 虚拟报表包的 Analysis Workspace 项目中的报表。
   > [!TIP] 虽然“客户属性”不能在 CDA 中使用，但这两项功能都依赖于 `setCustomerIDs` 函数。这两个功能可以在单独的虚拟报告套件中保持一致。
* CDA 需要使用协作图或专用图。不支持第三方设备图。
* 不支持旧版 Analytics ID。仅拼合具有 Experience Cloud ID 的访客。
* 跨设备分析使用虚拟报表包和报表时间处理，二者各有其自身的限制。有关具体限制的详细信息，请参阅[虚拟报表包](../vrs/vrs-about.md)和[报表时间处理](../vrs/vrs-report-time-processing.md)。
* 不支持 1.4 API。Power BI 连接器和 Report Builder 都依赖于 1.4 API，因此与 CDA 不兼容。
* 如果您的组织使用的是专用图，则拼合新设备需要长达 24 小时。
* 协作图需要长达两周的时间来处理访问您网站的新设备。CDA 中针对最近两周数据的拼合级别，通常低于两周以前的日期范围。
* 虚拟报表包中的历史数据会因 Adobe 识别和拼合的设备而发生变化。源报表包中的数据不会更改。

贵组织在满足所有要求并了解相关限制后，便可以开始[设置跨设备分析](cda-setup.md)。
