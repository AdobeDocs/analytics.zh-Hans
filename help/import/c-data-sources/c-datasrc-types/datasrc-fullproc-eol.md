---
title: 完全处理数据源的生命周期结束
description: 批量数据插入API与完全处理数据源之间链接和比较结束的原因。
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 9%

---


# 完全处理数据源的生命周期结束

多年来，“完全处理数据源”允许您向Adobe Analytics提交点击级别数据。 处理这些数据的方式与通过我们的JavaScript库和移动应用程序SDK收集的数据相同。 2020年，Adobe发布了[批量数据插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，该API执行与完全处理数据源相同的功能，但具有其他功能。 本主题提供有关批量数据插入API提供的其他功能的详细信息，并概述文件格式中的差异。

从2021年3月25日开始，Adobe将阻止创建新的完全处理数据源连接。 在服务完全弃用之前，将继续支持现有连接。 折旧将于2021年进行，但具体日期尚未确定。

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

| BDIA、FPDS和 | BDIA变量 | 完全处理列变量 | 描述 |
| --- | --- | --- | --- |
| BDIA | aamlh | 不受支持 | Adobe Audience Manager位置提示。 请参阅下面的AAM区域列表表中的有效ID值。 |
| Both | browserHeight | browserHeight | 浏览器高度（以像素为单位）（例如，768） |
| 两者 | browserWidth | browserWidth | 浏览器宽度（以像素为单位）（例如1024） |
| 两者 | campaign | 活动 | 转换活动跟踪代码 |
| 两者 | channel | 渠道 | 渠道字符串（例如，“体育节”） |
| 两者 | colorDepth | colorDepth | 以位为单位的显示器颜色深度（例如，24） |
| 两者 | connectionType | connectionType | 访客的连接类型（LAN或调制解调器） |
| BDIA | contextData.key | 不受支持 | 键值对通过命名标题“contextData.product”或“contextData.color”来指定 |
| 两者 | cookiesEnabled | cookieEnabled | `Y` 或 `N` 用于访客是否支持第一方会话Cookie |
| 两者 | currencyCode | currencyCode | 收入货币代码（例如`USD`） |
| BDIA | 客户ID。[customerIDType].authState | 不受支持 | 访客的已验证状态。 支持的值有：0、1、2、UNKNOWN、AUTHENTICATED、LOGGED_OUT或“（不区分大小写）。 两个连续的单引号(&quot;)导致从查询字符串中忽略该值，在进行点击时，该值转换为0。 请注意，支持的authState数值表示以下值： 0 = UNKNOWN， 1 = AUTHENTICATED， 2 = LOGGED_OUT。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
| BDIA | 客户ID。[customerIDType].id | 不受支持 | 要使用的客户ID。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
| BDIA | 客户ID。[customerIDType].isMCSeed | 不受支持 | 这是否是Marketing Cloud访客ID的种子。 支持的值为：0、1、TRUE、FALSE、“（不区分大小写）。 使用0、FALSE或两个连续的单引号(&quot;)会导致从查询字符串中忽略该值。 customerIDType可以是任何字母数字字符串，但应视为区分大小写。 |
