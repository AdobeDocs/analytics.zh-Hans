---
title: 跨设备分析
description: 了解如何通过将设备数据拼合在一起，将您的数据从以设备为中心更改为以人员为中心。
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: 6c74f4d4c14765742a2aafdfff2a083c6b0a7183
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 57%

---

# 跨设备分析

{{available-existing-customers}}

>[!WARNING]
>
>跨设备分析中的设备图在&#x200B;**2025年12月31日**&#x200B;将不再可用。 请将当前任何启用“设备图”的VRS切换到基于[字段的方法](/help/components/cda/field-based-stitching.md)。
>


跨设备分析 (CDA) 是一项功能，可将 Analytics 从以设备为中心的视图转变为以人员为中心的视图。 因此，分析师可以了解跨浏览器、设备或应用程序的用户行为。Adobe 支持使用两个主要工作流程，将设备数据链接在一起：

* [**基于字段的拼接**](field-based-stitching.md)：推荐使用的拼接选项，因为它仅使用确定性匹配将设备联系在一起。基于字段的拼接允许您选择一个Analytics变量作为在虚拟报表包中跨设备拼接的基础。

* [**设备图**](device-graph.md)： Cross-Device Analytics与专用图通信以将设备拼接在一起。

通过使用 CDA，您可以回答类似下面的问题：

* 有多少人与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的营销活动点进次数是否会导致转换到其他设备上？
* 如果考虑跨设备历程，我对营销活动效用的理解会有怎样的变化？我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？

当设备拼合在一起后，变量持久性会在设备之间传递。例如，用户首先通过台式计算机上的广告访问了您的网站。然后，该用户找到并安装了您的移动设备应用程序，而且最终在其移动设备上进行了购买。对于 Cross-Device Analytics，可将移动设备上的收入归因于用户在其桌面计算机上单击的广告。

Microsoft Azure用于Cross-Device Analytics。 Adobe 使用 Azure 存储设备图数据并执行跨设备拼合。因此，Adobe Analytics数据在Adobe的数据处理中心和Adobe配置的Microsoft Azure实例之间来回传递。

请参阅[Cross-Device Analytics Spark页面](https://express.adobe.com/page/8ZpjsX6Lp5XTM/)，了解有关Cross-Device Analytics功能和特征的详细信息。

## 先决条件

使用跨设备分析需要[基于字段的拼合](field-based-stitching.md)和[设备图](device-graph.md)方法，并且两者都有各自的特定先决条件。

* 必须与 Adobe 签订有关 Adobe Analytics Ultimate 的合同。
* 您的组织选择要启用 CDA 的报告包。 Adobe建议报表包中包含跨设备数据，即，来自多种设备/浏览器/应用程序类型的数据。 虽然从地理角度来说，Cross-Device Analytics并不一定需要具有严格全局性，但一些组织将此概念称为“全局”报表包。

## 限制

Cross-Device Analytics 是一项具有突破性的强大功能，但其使用方式存在限制。[基于字段的拼合](field-based-stitching.md)以及[设备图](device-graph.md)方法还有其各自的特定限制。

* Cross-Device Analytics只能通过Analysis Workspace使用。
* Cross-Device Analytics 不适用于多个报表包，也无法合并多个报表包的数据。
* Adobe Analytics 报告包无法映射到多个组织 ID。由于跨设备分析拼合给定报表包中的设备，因此跨设备分析无法用于拼合多个组织ID之间的数据。
* 跨设备分析使用复杂的处理管道，并具有多个依赖组件。 此管道与基本Analytics报告工作流并行运行。 预计源报表包和Cross-Device Analytics虚拟报表包之间的点击总数的数据不匹配率约为1%。
* Cross-Device Analytics 使用虚拟报表包和报表时间处理，二者各有其自身的限制。例如，它们目前不支持营销渠道变量。有关具体限制的详细信息，请参阅[虚拟报表包](/help/components/vrs/vrs-about.md)和[报表时间处理](/help/components/vrs/vrs-report-time-processing.md)。
* 专用图形利用Experience Cloud和Adobe Analytics中的[客户属性](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/services/customer-attributes/attributes)功能所使用的相同ID同步。 但是，Cross-Device Analytics虚拟报表包（无论是基于专用图形还是基于字段的拼接）与其余的“客户属性”功能不兼容。 换句话说，基于客户属性的维度不可用于Cross-Device Analytics虚拟报表包。
* Cross-Device Analytics当前与A4T不兼容。
* 不支持 1.4 API。Power BI 连接器和 Report Builder 都依赖于 1.4 API，因此与 CDA 不兼容。
* Adobe对跨设备分析拼合过程的主动监视仅适用于生产报表包。
* Cross-Device Analytics当前与Adobe Analytics [数据修复API](https://developer.adobe.com/analytics-apis/docs/2.0/)不兼容
* 虚拟报表包中的历史数据会因 Adobe 识别和拼合的设备而发生变化。源报表包中的数据不会更改。
* 拼合的数据遵循 8 到 12 小时的延迟。
* 给定设备的映射历史记录数据最长存储 1 年。
* 如果设备在一年内产生的映射历史记录条目非常多，则映射历史记录将被截断。确切的限制取决于所使用的拼接选项。
