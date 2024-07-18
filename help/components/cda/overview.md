---
title: Cross-Device Analytics
description: 通过将设备数据拼合在一起，将您的数据从以设备为中心更改为以人员为中心。
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 90%

---

# Cross-Device Analytics

跨设备分析 (CDA) 是一项功能，可将 Analytics 从以设备为中心的视图转变为以人员为中心的视图。 因此，分析师可以了解跨浏览器、设备或应用程序的用户行为。Adobe 支持使用两个主要工作流程，将设备数据链接在一起：

* [**基于字段的拼接**](field-based-stitching.md)：推荐使用的拼接选项，因为它仅使用确定性匹配将设备联系在一起。使您可选择 Analytics 变量作为在虚拟报表包中进行跨设备拼接的基础。

* [**设备图**](device-graph.md)：CDA 与专用图通信以将设备拼接在一起。

通过使用 CDA，您可以回答类似下面的问题：

* 有多少人与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的营销活动点进次数是否会导致转换到其他设备上？
* 如果考虑跨设备历程，我对营销活动效用的理解会有怎样的变化？我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？

当设备拼合在一起后，变量持久性会在设备之间传递。例如，用户首先通过台式计算机上的广告访问了您的网站。然后，该用户找到并安装了您的移动设备应用程序，而且最终在其移动设备上进行了购买。对于 Cross-Device Analytics，可将移动设备上的收入归因于用户在其桌面计算机上单击的广告。

本着合作精神和透明精神，我们希望客户了解我们与 Cross-Device Analytics 相结合使用的 Microsoft Azure。Adobe 使用 Azure 存储设备图数据并执行跨设备拼合。因此，Adobe Analytics数据在Adobe的数据处理中心和Adobe配置的Microsoft Azure实例之间来回传递。

请参阅[历程 IQ：Cross-Device Analytics Spark 页面](https://adobe.ly/aacda)，了解关于 Cross-Device Analytics 功能和特征的详细信息。

## 先决条件

使用 CDA 需要满足以下所有条件。[基于字段的拼合](field-based-stitching.md)以及[设备图](device-graph.md)方法还有其各自的特定先决条件。

* 必须与 Adobe 签订有关 Adobe Analytics Ultimate 的合同。
* 您的组织选择要启用 CDA 的报告包。 Adobe 建议报告包包含跨设备数据，这表示数据来自多种设备/浏览器/应用程序类型。 某些组织将此概念称为“全球”报表包，尽管从地理角度来说，CDA 并不一定包含严格意义上的全球范围。

## 限制

Cross-Device Analytics 是一项具有突破性的强大功能，但其使用方式存在限制。[基于字段的拼合](field-based-stitching.md)以及[设备图](device-graph.md)方法还有其各自的特定限制。

* CDA 仅通过 Analysis Workspace 提供。
* Cross-Device Analytics 不适用于多个报表包，也无法合并多个报表包的数据。
* Adobe Analytics 报告包无法映射到多个组织 ID。由于 CDA 拼合给定报告包内的设备，因此 CDA 无法用于拼合多个组织 ID 之间的数据。
* CDA 使用复杂的处理管道，并具有多个依赖组件。这与基本 Analytics 报告工作流并行运行。因此，预计源报表包和 CDA 虚拟报表包之间的点击总数的数据不匹配率约为 1%。
* Cross-Device Analytics 使用虚拟报表包和报表时间处理，二者各有其自身的限制。例如，它们目前不支持营销渠道变量。有关具体限制的详细信息，请参阅[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hans)和[报表时间处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html#report-time-processing-limitations?lang=zh-Hans)。
* 专用图形利用Experience Cloud和Adobe Analytics中的[客户属性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hans#customer-attributes)功能所使用的相同ID同步。 但是，CDA虚拟报表包（无论是基于专用图形还是基于字段的拼接）与其余的“客户属性”功能不兼容。 换句话说，基于客户属性的维度不可用于CDA虚拟报表包。
* CDA 当前与 A4T 不兼容。
* 不支持 1.4 API。Power BI 连接器和 Report Builder 都依赖于 1.4 API，因此与 CDA 不兼容。
* Adobe 对于 CDA 拼合过程的主动监视仅适用于生产报表包。
* CDA 当前与 Adobe Analytics [数据修复 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md) 不兼容
* 虚拟报表包中的历史数据会因 Adobe 识别和拼合的设备而发生变化。源报表包中的数据不会更改。
* 拼合的数据遵循 8 到 12 小时的延迟。
* 给定设备的映射历史记录数据最长存储 1 年。
* 如果设备在一年内产生的映射历史记录条目非常多，则映射历史记录将被截断。确切的限制取决于所使用的拼接选项。
