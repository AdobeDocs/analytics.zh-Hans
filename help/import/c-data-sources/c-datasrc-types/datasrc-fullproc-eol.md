---
title: Full Processing Data Sources 生命周期结束
description: 终止使用的原因以及 Bulk Data Insertion API 与 Full Processing Data Sources 之间的对比。
feature: Data Sources
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 97%

---

# Full Processing Data Sources 生命周期结束

多年来，您可以利用 Full Processing Data Sources 向 Adobe Analytics 提交点击级别的数据。此数据的处理方式与通过我们 JavaScript 库和移动应用程序 SDK 收集的数据的处理方式相同。2020 年，Adobe 发布了 [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，它执行与 Full Processing Data Sources 相同的功能，不过还提供了附加功能。本主题介绍有关 Bulk Data Insertion API 所提供附加功能的详细信息，并概述了文件格式上的差别。

自 2021 年 3 月 25 日开始，Adobe 禁止创建新的 Full Processing Data Sources 连接。现有连接仍受支持，直至 2022 年 1 月 31 日完全弃用。除了标准文档之外，我们还提供[通过 Bulk Data Insertion API 提交数据所需步骤](https://adobe.ly/aabdia)的演练。

## 为什么我们要终止使用此功能？

Bulk Data Insertion API (BDIA) 涵盖了 Full Processing 支持的所有功能，此外还提供了附加功能。使用 Bulk Data Insertion API，您可以获得更好的服务。

## Full Processing Data Sources 与 Bulk Data Insertion API 之间的主要差别。

* Bulk Data Insertion 允许提交多个文件来并行处理。您可以使用访客组来确保访客连续性和 eVar 归因。
* Bulk Data Insertion 具有数据验证和错误处理功能，从而消除了提交点击数据中的一些管理工作。
* Bulk Data Insertion 支持访客 ID 的多个选项。您可以同时提交 Analytics ID 和 Marketing Cloud ID（有关详细信息，请参阅[身份服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)）。此外，您可以使用自己的 ID 作为[生成 ECID 的种子](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* Bulk Data Insertion 支持列表和上下文数据变量。
* Bulk Data Insertion 不支持 Activity Map 数据。

## 文件格式和内容中的主要差别

* Bulk Data Insertion 有一些额外的必填字段。有关详细信息，请参阅[文档](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)。
* 为确保访客连续性和归因，Bulk Data Insertion 要求文件中的行以时间排序。如需了解跨多个文件对访客活动排序，请参阅[访客组](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)。
* Bulk Data Insertion 需要以 .gzip 格式压缩的 .csv 文件。
* BDIA 使用“timestamp”而不是“date”。

有关详细信息，请参阅 Bulk Data Insertion (BDIA) 和 Full Processing Data Sources (FPDS) 中提供的以下字段值的对比。

## BDIA 和 FPDS 中可用的字段值对比

| BDIA 变量 | 完全处理列变量 | 描述 |
| --- | --- | --- |
| aamlh | 不支持 | Adobe Audience Manager 位置提示。 |
| browserHeight | browserHeight | 浏览器高度，以像素为单位（例如，768） |
| browserWidth | browserWidth | 浏览器宽度，以像素为单位（例如，1024） |
| campaign | 营销活动 | 转化营销活动跟踪代码 |
| channel | 频道 | 渠道字符串（例如，体育专栏） |
| colorDepth | colorDepth | 显示器颜色深度，以位为单位（例如，24） |
| connectionType | connectionType | 访客的连接类型（LAN 或调制解调器） |
| contextData.key | 不支持 | 通过指定标题“contextData.product”或“contextData.color”的方式来指定的键值对。 |
| cookiesEnabled | cookiesEnabled | `Y` 或 `N`，表示访客是否支持第一方会话 Cookie |
| currencyCode | currencyCode | 收入货币代码（例如，`USD`） |
| customerID.[customerIDType].authState | 不支持 | 访客的身份验证状态。支持的值为：0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT 或 &#39;&#39;（不区分大小写）。两个连续的单引号 (&#39;&#39;) 会从查询字符串中忽略该值，这会在发生点击操作时转换为 0。请注意，支持的 authState 数值表示以下值：0 = UNKNOWN，1 = AUTHENTICATED，2 = LOGGED_OUT。customerIDType 可以是任意字母数字字符串，但应视为区分大小写。 |
| customerID。[customerIDType].id | 不支持 | 要使用的客户 ID。customerIDType 可以是任意字母数字字符串，但应视为区分大小写。 |
| customerID。[customerIDType].isMCSeed | 不支持 | 此项是否为 Marketing Cloud 访客 ID 的种子。支持的值为：0、1、TRUE、FALSE、&#39;&#39;（不区分大小写）。使用 0、FALSE 或两个连续的单引号 (&#39;&#39;) 会从查询字符串中忽略该值。customerIDType 可以是任意字母数字字符串，但应视为区分大小写。 |
| eVarN | eVarN，即 `<eVar2>`...`<eVar>` | 转化 eVar 名称。您最多可有 75 个 eVar (eVar1 - eVar75) 您可以指定 eVar 名称 (eVar12) 或友好名称（广告营销活动 3）。 |
| events | 事件 | [事件字符串](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html#vars)，使用与 s.events 变量相同的语法进行格式设置。例如：scAdd,event1,event7 |
| hierN | hierN，即 `<hier2>`…`</hier2>` | 层级名称。您最多可有 5 个层级 (hier1 - hier5）。您可以指定默认层级名称 `hier2` 或友好名称 (Yankees)。 |
| homePage | homePage | Y 或 N — 当前页面是否为访客的主页。 |
| ipaddress | 不支持 | 访客的 IP 地址。 |
| javaEnabled | javaEnabled | Y 或 N — 访客是否已启用 Java。 |
| javaScriptVersion | javaScriptVersion | JavaScript 版本（例如 1.3）。 |
| language | 不支持 | 浏览器支持的语言。例如：`en-us`。 |
| linkName | linkName | 链接名称。 |
| linkType | linkType | 链接类型。支持的值包括： `d: Download link`, `e: Exit link`, `o: Custom link`。 |
| linkURL | linkURL | 链接的 HREF。 |
| listn，例如 list2。 | 不支持 | 传入变量中的包含分隔的值列表，然后作为报告中的单独行项目报告 |
| marketingCloudVisitorID | 不支持 | Marketing Cloud ID。请参阅[访客识别](https://experienceleague.adobe.com/docs/id-service/using/home.html#id-service-api)和 Marketing Cloud 访客 ID 服务 |
| 不支持 | charSet | 您的网站支持的字符集。例如，UTF-8、ISO-8859-1 等。 |
| 不支持 | clickAction | 访客点击图的对象标识符 (oid) |
| 不支持 | clickActionType | 访客点击图的对象标识符类型 (oidt) |
| 不支持 | clickContext | 访客点击图的页面标识符 (pid) |
| 不支持 | clickContextType | 访客点击图的页面标识符类型 (pidt) |
| 不支持 | clickSourceID | 访客点击图的源索引 (oi) |
| 不支持 | clickTag | 访客点击图的对象标记名称 (ot) |
| 不支持 | scXmlVer | 市场营销报表 XML 请求版本号（例如 1.0）。 |
| 不支持 | timezone | 访客所在时区与格林威治时间的小时差（例如 -8）。 |
| pageName | pageName | 页面的名称 |
| pageType | pageType | 页面的类型（例如，“错误页面”）。 |
| pageUrl | pageUrl | 页面 URL（例如，https://www.example.com/index.html）。 |
| plugins | plugins | 分号分隔的浏览器插件名称列表。 |
| products | 产品 | 页面上所有产品的列表。使用逗号分隔产品。例如：Sports;Ball;1;5.95,Toys; Top;1:1.99。 |
| prop1-prop75 | propN，即 `<prop2>`…`</prop2>` | 属性 N 字符串（例如，体育专栏）。 |
| propN | propN | 属性的属性值。 |
| purchaseID | purchaseID | 购买 ID 号码。 |
| referrer | 反向链接 | 页面反向链接的 URL。 |
| reportSuiteID | s_account | 指定要提交数据的报表包。应使用逗号来分隔多个报告包 ID。 |
| resolution | resolution | 显示器分辨率（例如 1024x768）。 |
| server | 服务器 | 服务器字符串。 |
| state | state | 转化州字符串。 |
| timestamp | 日期 | 使用 ISO 8601 日期格式 YYYY-MM-DDThh:mm:ss±UTC_offset（例如，2021-09-01T12:00:00-07:00），或者 Unix 时间格式（自 1970 年 1 月 1 日以来经过的秒数）。 |
| trackingServer | 不支持 | 只能通过列标题提供。 |
| transactionID | 不支持 | 用于将多渠道用户活动绑定在一起作报告之用的公用值。有关更多信息，请参阅[数据源用户指南](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html#data-sources)。 |
| userAgent | 不支持 | 用户代理字符串 |
| visitorID | visitorID | 访客的 Analytics ID。请参阅[访客识别](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 |
| zip | zip | 转化邮政编码。 |
