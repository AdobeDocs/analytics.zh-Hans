---
title: 完全处理数据源的生命周期结束
description: 批量数据插入API与完全处理数据源之间链接和比较结束的原因。
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
translation-type: tm+mt
source-git-commit: 03a2b346dc6940bc7471de454f73c58f5462a0bb
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 29%

---

# 完全处理数据源的生命周期结束

多年来，“完全处理数据源”允许您向Adobe Analytics提交点击级别数据。 处理这些数据的方式与通过我们的JavaScript库和移动应用程序SDK收集的数据相同。 2020年，Adobe发布了[批量数据插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，该API执行与完全处理数据源相同的功能，但具有其他功能。 本主题提供有关批量数据插入API提供的其他功能的详细信息，并概述文件格式中的差异。

从2021年3月25日开始，Adobe将阻止创建新的完全处理数据源连接。 在2021年7月31日服务完全弃用之前，将继续支持现有连接。

## 为什么我们要终止使用此功能？

批量数据插入API(BDIA)提供附加功能，同时涵盖完全处理支持的所有用例。 我们相信，使用批量数据插入API将为您提供更好的服务。

## 完全处理数据源与批量数据插入API之间的主要区别

* “批量数据插入”允许提交多个可并行处理的文件。 您可以使用访客组来确保访客连续性和eVar归因。
* 批量数据插入具有数据验证和错误处理功能，从而消除了提交点击数据的一些管理工作。
* “批量访客插入”支持多个用于数据ID的选项。 您可以提交Analytics ID和Marketing CloudID（请参阅[Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)了解更多信息）。 此外，您可以使用您自己的ID作为[种子来生成ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds)。
* 批量数据插入支持列表和上下文数据变量。
* 批量Activity Map插入不支持数据。

## 文件格式和内容方面的主要差异

* “批量数据插入”包含一些其他必填字段。 有关详细信息，请参阅[文档](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)。
* 为确保访客的连续性和归因，“批量数据插入”要求按时间顺序对文件中的行进行排序。 请参阅[访客组](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups)了解跨文件访客活动的顺序。
* “批量数据插入”要求文件以.gzip格式进行.csv压缩。
* BDIA使用“timestamp”而不是“date”。

有关详细信息，请参阅批量数据插入(BDIA)和完全处理数据源(FPDS)中可用字段值的以下比较。

## BDIA和FPDS中可用字段值的比较

| BDIA变量 | 完全处理列变量 | 描述 |
| --- | --- | --- |
| aamlh | 不受支持 | Adobe Audience Manager位置提示。 |
| browserHeight | browserHeight | 浏览器高度（以像素为单位）（例如，768） |
| browserWidth | browserWidth | 浏览器宽度（以像素为单位）（例如1024） |
| campaign | 活动 | 转换活动跟踪代码 |
| channel | 渠道 | 渠道字符串（例如，“体育节”） |
| colorDepth | colorDepth | 以位为单位的显示器颜色深度（例如，24） |
| connectionType | connectionType | 访客的连接类型（LAN或调制解调器） |
| contextData.key | 不受支持 | 键值对通过命名标题“contextData.product”或“contextData.color”来指定 |
| cookiesEnabled | cookieEnabled | `Y` 或 `N` 用于访客是否支持第一方会话Cookie |
| currencyCode | currencyCode | 收入货币代码（例如`USD`） |
| 客户ID。[customerIDType].authState | 不受支持 | 访客的已验证状态。 支持的值有：0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT或“（不区分大小写）。 两个连续的单引号(&quot;)导致从查询字符串中忽略该值，在进行点击时，该值转换为0。 请注意，支持的authState数值表示以下值： 0 = UNKNOWN， 1 = AUTHENTICATED， 2 = LOGGED_OUT。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
| 客户ID。[customerIDType].id | 不受支持 | 要使用的客户ID。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
| 客户ID。[customerIDType].isMCSeed | 不受支持 | 这是否是Marketing Cloud访客ID的种子。 支持的值为：0、1、TRUE、FALSE、“（不区分大小写）。 使用0、FALSE或两个连续的单引号(&quot;)会导致从查询字符串中忽略该值。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
| eVarN | eVarN，即`<eVar2>`...`<eVar>` | 转化 eVar 名称。您最多可有 75 个 eVar ( eVar1 - eVar75)可以指定eVar名称(eVar12)或友好名称(广告活动3)。 |
| events | 事件 | [事件字符串](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars)，格式采用与s.事件变量相同的语法。例如：scAdd，事件1,事件7 |
| hierN | hierN，即`<hier2>`..`</hier2>` | 层级名称。您最多可有 5 个层级 ( hier1 - hier5)。 您可以指定默认层次结构名称`hier2`或友好名称（洋基队）。 |
| homePage | homePage | Y 或 N - 当前页面是否为访客的主页。 |
| ipaddress | 不受支持 | 访客的IP地址。 |
| javaEnabled | javaEnabled | Y 或 N - 访客是否已启用 Java。 |
| javaScriptVersion | javaScriptVersion | JavaScript 版本（例如 1.3）。 |
| language | 不受支持 | 浏览器支持的语言。 例如：`en-us`。 |
| linkName | linkName | 链接名称。 |
| linkType | linkType | 链接类型。支持的值包括：  `d: Download link`,  `e: Exit link`,  `o: Custom link` |
| linkURL | linkURL | 链接的 HREF。 |
| 列表例如，列表2。 | 不受支持 | 一个分隔的值列表，这些值会传入一个变量，然后报告为单独的行项目以便制作报表。 |
| marketingCloudVisitorID | 不受支持 | Marketing Cloud ID. 请参阅[访客标识](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api)和Marketing Cloud访客ID服务。 |
| 不受支持 | charSet | 网站支持的字符集。 例如，UTF-8、ISO-8859-1 等。 |
| 不受支持 | clickAction | 访客点击图的对象标识符 (oid) |
| 不受支持 | clickActionType | 访客点击图的对象标识符类型 (oidt) |
| 不受支持 | clickContext | 访客点击图的页面标识符 (pid) |
| 不受支持 | clickContextType | 访客点击图的页面标识符类型 (pidt) |
| 不受支持 | clickSourceID | 访客点击图的源索引 (oi) |
| 不受支持 | clickTag | 访客点击图的对象标记名称 (ot) |
| 不受支持 | scXmlVer | 市场营销报表 XML 请求版本号（例如 1.0）。 |
| 不受支持 | timezone | 访客所在时区与格林威治时间的小时差（例如 -8）。 |
| pageName | pageName | 页面的名称。 |
| pageType | pageType | 页面的类型（例如“错误页面”）。 |
| pageUrl | pageUrl | 页面URL(例如，https://www.example.com/index.html)。 |
| plugins | 插件 | 以分号分隔的浏览器插件名称列表。 |
| products | 产品 | 列表页面上的所有产品。 用逗号分隔产品。 例如：运动；球；1;5.95，玩具；顶部；1:1.99。 |
| prop1 - prop75 | propN，即`<prop2>`..`</prop2>` | 属性#字符串（例如，“体育节”）。 |
| propN | propN | 属性的属性值。 |
| purchaseID | purchaseID | 购买 ID 号码。 |
| referrer | 推荐人 | 页面反向链接的 URL。 |
| reportSuiteID | s_account | 指定要提交数据的报表包。您应用逗号分隔多个报表包ID。 |
| resolution | 分辨率 | 显示器分辨率（例如 1024x768）。 |
| server | 服务器 | 服务器字符串。 |
| state | 状态 | 转化州字符串。 |
| timestamp | 日期 | 使用YYYY-MM-DDTh:mm:ss±UTC_offset(例如2021-09-01T12:00:00-07:00)的ISO 8601日期格式或Unix时间格式（自1970年1月1日起已用的秒数）。 |
| trackingServer | 不受支持 | 只能通过列标题提供。 |
| transactionID | 不受支持 | 用于将多渠道用户活动绑定在一起作报告之用的公用值。有关详细信息，请参阅[Data Sources用户指南](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources)。 |
| userAgent | 不受支持 | 用户代理字符串 |
| visitorID | visitorID | 访客的分析ID。 请参阅[访客标识](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en)。 |
| zip | zip | 转化邮政编码。 |
