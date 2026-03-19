---
title: Adobe Analytics 中处理数据的顺序
description: 了解在 Adobe Analytics 中处理数据的组件和服务的顺序。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 35%

---

# Adobe Analytics 中处理数据的顺序

Adobe 提供多种方式，可在报表中出现数据之前更改或操纵数据。此页面展示各项 Adobe Analytics 功能处理数据的顺序。可使用此列表解决数据不一致的问题或确定最适合在需要调整数据时使用的功能。

![正在处理订单图像](assets/processing-order.png)

## 将数据发送到 Adobe 之前

将数据发送到 Adobe 之前，自动使用以下方法之一在客户端编译数据：

* **AppMeasurement**：一个托管在您的站点上并在每个页面上都引用的 JavaScript 文件。数据直接发送到 Adobe Analytics。
* **Adobe Experience Platform Web SDK**：一个托管在您的站点上并在每个页面上都引用的 JavaScript 文件。数据会发送到Adobe Experience Platform Edge Network。
* Adobe Experience Platform数据收集中的&#x200B;**标记**：一个在每个页面上引用的JavaScript文件，其中包含在数据收集UI中创建的规则。 Adobe Analytics 扩展提供一种更容易实施 AppMeasurement 的方式。Web SDK 扩展提供一种更容易实施 Web SDK 的方式。
* **API**： AppMeasurement和Edge Network均提供编程方法将数据发送到Adobe。 AppMeasurement提供[数据插入API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/)和[批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)；Edge Network提供[数据收集API](https://developer.adobe.com/data-collection-apis/docs/)。

如果将数据发送到Edge Network，则可将其配置为将数据转发到Adobe Analytics（以及许多其他Adobe Experience Cloud解决方案）。 无论采用何种实施方法，收集的点击数据最终都会以可解析的格式到达Adobe Analytics处理服务器。

## Adobe Analytics收藏集中的预处理

当数据到达Adobe Analytics时，它会进入预处理阶段：

1. [**动态变量**](/help/implement/vars/page-vars/dynamic-variables.md)：如果在图像请求的任何部分中发现动态变量，则将其值复制过来，并且以后它其视为独立的值。
1. [**IP模糊处理（最后一个八位字节）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的报表包配置为仅模糊处理最后一个八位字节，则该模糊处理在此处适用。 请注意，IP模糊处理（删除IP）稍后会在处理管道中发生。
1. **查找表**：依赖于Adobe内部查找表的维度（例如[浏览器](/help/components/dimensions/browser.md)维度）与其相应的值匹配。
1. [**IP排除**](/help/admin/tools/exclude-ip.md)：在此步骤中会标记您明确从报表中排除的任何IP地址。
1. [**机器人规则**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)：应用标准或自定义机器人筛选以从报表中排除这些数据。
1. **地理位置数据**：填充依赖于 IP 地址查找的维度（例如[国家/地区](/help/components/dimensions/countries.md)维度）。
1. [**处理规则**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)：您的组织应用于您的数据的自定义规则。包括[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)与其各自的Analytics变量的映射。
1. [**VISTA 规则**](vista.md)：Adobe 顾问应用于您的数据的自定义灵活规则。可在处理规则前后运行 VISTA 规则，具体取决于您组织的需要。大多数 VISTA 规则一般都在处理规则之后运行，但每个组织的设置有所不同。有关现有VISTA规则的更多信息，请与您的Adobe客户团队联系。
1. **货币转换**：如果点击包含的[`currencyCode`](/help/implement/vars/config-vars/currencycode.md)与报表包中使用的货币不同，则任何适用的货币变量都将使用当天的汇率进行转换。
1. [**邮政编码**](/help/components/dimensions/zip-code.md)：根据报表包设置填充“邮政编码”维度。

## 数据收集管道的“中值”阶段

预处理完成后，若干功能会使用此经过部分处理的数据形式（称为“中间值”）。 在将数据发送到任何位置之前，将应用一些特定于中间值的处理：

1. [**点击级别的营销渠道处理规则**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：这些处理规则专门针对Analytics Source Connector运行。 由于还没有访问或访客级别的上下文，因此这些处理规则假定点击不是访问的首次点击。 在`channel.typeAtSource`和`channel._id`中提供了针对点击运行处理规则的结果。
1. [**IP模糊处理（删除IP）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的报表包配置为完全模糊处理IP地址，则该模糊处理在此处适用（仅适用于mid值）。

此时，中值数据将发送到其相应的功能：

* [**Livestream API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)：在收集数据流时，将应用程序连接到Adobe的Livestream服务。
* [**Analytics Source Connector**](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/analytics)：将Adobe Analytics报表包数据摄取到Adobe Experience Platform数据集。
* [**实时报表**](/help/components/c-real-time-reporting/realtime.md)：在Analysis Workspace中最多提供三个可配置的实时报表。

## 访问和访客级别的处理

到目前为止，给定点击不了解在该点击之前或之后收集的点击或点击上下文。 此处理阶段会填充访问和访客级别的字段。

1. [**访问+访客定义**](/help/implement/id/overview.md)：根据点击包含的访客变量识别点击。
1. [**访问次数**](/help/components/dimensions/visit-number.md)：根据已识别访客的其他访问次数，计算访问次数。
1. **事件去重**：如果点击包含重复的[`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)或[事件序列化](/help/implement/vars/page-vars/events/event-serialization.md)，则将检查这些ID并分别对其进行标记。
1. [**访问级别的营销渠道处理规则**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)：每次点击都通过营销渠道处理规则运行，并且其渠道+渠道详细信息将确定点击是否与任何规则匹配。 这些规则填充Analysis Workspace中可用的[营销渠道](/help/components/dimensions/marketing-channel.md)和[营销渠道详细信息](/help/components/dimensions/marketing-detail.md)维度。
1. **变量持久性**：对于具有持久性（如[eVars](/help/components/dimensions/evar.md)）的维度，该值在此步骤中确定。 一般而言，此处设置了大多数`post`值。
1. **交易ID**：如果点击包含新的[`transactionID`](/help/implement/vars/page-vars/transactionid.md)值，则存储所有受支持值的“快照”。 当数据源上载包含匹配的事务ID时，该数据源行中将包含此快照支持的所有值。
1. [**IP模糊处理（删除IP）**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)：如果您的报表包配置为完全模糊处理IP地址，则在所有其他处理完成后将在此处应用该模糊处理。

此时，将这次单独的点击记录在报表包数据表中。在标准[延迟](latency.md)间隔过后，可在报表中找到它。

## 处理数据之后更改数据

Adobe Analytics 中的数据大多为永久数据；但是，通过某些功能可选择性地调整或删除数据：

* [**数据修复 API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：编辑数据的某些列或删除数据中所需的行。
* [**数据管理**](/help/technotes/privacy/privacy-overview.md)：考虑到隐私请求而永久删除数据。
* [**分类**](/help/components/classifications/classifications-overview.md)：根据规则或上传的数据创建维度，这样使您可按不同方式组织数据。不更改报表套件的底层数据，因此您可随意编辑或覆盖分类数据。
* [**虚拟报表包**](/help/components/vrs/vrs-about.md)：创建可更改访问超时的备用报表包视图。
