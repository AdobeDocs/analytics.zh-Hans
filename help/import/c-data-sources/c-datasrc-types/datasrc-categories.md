---
description: 数据源类别标识提供相似功能的不同数据源类型。
subtopic: Data sources
title: 数据类型和类别概述
topic-fix: Developer and implementation
feature: Data Sources
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '903'
ht-degree: 100%

---

# 数据类型和类别概述

数据源类别标识提供相似功能的不同数据源类型。

通过类别，可以从用户的角度对数据源进行分组。通过 [!DNL Data Sources] UI 创建数据源时，请首先选择数据源类别，然后指定数据源类型。每个类别都包含多种支持相似数据类型的数据源类型。[!DNL Data Sources] 提供以下数据源类别：

## 网站使用 {#web-usage}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 网站服务器日志文件] | [网络日志](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | 大多数网站服务器都会生成日志文件，其中记录了所提供的每一个页面。使用该数据源，您可以处理来自大多数网站服务器数据的日志文件，并将该数据添加到您的报表中。 |
| [!UICONTROL Advertising Cloud 批量上传] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 提供 [!DNL Advertising Cloud] 中的手动和 Excel 自动批量上传。 |
| [!UICONTROL 站点级别流量数据源] | [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 导入整个网站的流量数据。例如，[!UICONTROL 页面查看次数]。 |
| [!UICONTROL 划分流量数据源] | [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | 导入由其他网站变量划分的流量数据。例如，按[!UICONTROL 产品]细分的[!UICONTROL 页面查看次数]。 |

## 广告营销活动 {#ad-campaigns}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 通用广告服务器] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将涉及广告服务器上的广告服务活动的显示次数及其他首要量度集成到市场营销报表中。该数据源是通用的广告服务器数据源，如果您的特定广告服务器不在支持之列，应使用该数据源。 |
| [!UICONTROL 通用电子邮件营销活动服务器] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将电子邮件营销活动服务器中的量度集成到市场营销报表中。通常合成量度包括已发送、已递送和已阅读邮件的数量。该数据源是通用的电子邮件营销活动数据源，如果您的特定电子邮件营销活动服务器不在支持之列，应使用该数据源。 |
| [!UICONTROL 每次点击付费一般服务] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您导入有关每次点击付费绩效（包括显示次数、点击量和成本）的数据。该数据源是通用的每次点击付费数据源，如果您的特定每次点击付费服务不在支持之列，应使用该数据源。 |

## 客户关系管理 (CRM) {#crm}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 通用呼叫中心] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将有关呼叫中心的信息集成到市场营销报表中。通常导入的量度包括呼叫次数、通话时间、代理商和销售总额。该数据源是通用的呼叫中心数据源，如果您的特定呼叫中心软件不在支持之列，应使用该数据源。 |
| [!UICONTROL 通用客户支持应用程序] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将客户支持软件中的信息集成到市场营销报表中。它包括某些量度，如新事件的数量、已解决事件的数量和解决事件所花费的时间。该数据源是通用的客户支持数据源，如果您的特定客户服务应用程序不在支持之列，应使用该数据源。 |

## 客户满意度 {#csat}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 普通调查数据] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将来自第三方工具的调查结果集成到市场营销报表中，并通过客户与您的网站之间的交互情况显示客户的满意度。该数据源是通用调查数据源，如果您的特定调查数据服务不在支持之列，应使用该数据源。 |

## 网站性能 {#performance}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 普通网站下载速度] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您将来自跟踪下载速度的应用程序或服务的数据集成到您的数据。该数据源是通用下载速度数据源，如果您的特定下载速度软件或服务不在支持之列，应使用该数据源。 |

## 通用 {#generic}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 通用数据源（仅限概要数据）] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 如果没有数据源更匹配要导入市场营销报告与分析的数据类型，则使用该数据源。 |
| [!UICONTROL 通用数据源 (Full Processing)] | Full Processing | Adobe 将在 2022 年 1 月 31 日弃用 Full Processing Data Sources。[了解详情](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md)。Adobe 推荐改为使用 [Bulk Data Insertion API (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| [!UICONTROL 通用数据源（交易 ID）] | <ul><li>交易 ID</li><li>访客 ID</li></ul> | 允许您将任何离线事件绑定到在线事件。[!UICONTROL 交易 ID] 用作离线和在线事件之间的键。 |

## 在线购买 {#purchases}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 退货] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您导入退货数据，并将其与购买 ID 关联，这样您就可以确定搜索引擎、关键词、营销活动及其他更有可能产生退货的属性。 |
| [!UICONTROL 产品成本] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您提供从您的网站购买和发出的产品的实际成本。将成本或利润与单个产品相关联后，即可精确地报告网站中利润率最高的促销活动、关键词和内部促销活动。 |
| [!UICONTROL 订购状态] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您使用量度确认每个订购的状态，包括被取消、已发货、已完成或属欺诈行为的订购。订购状态报告功能可以确定哪些赢取方法产生的订购完成率最高。 |

## 商机和报价 {#leads}

| 数据源 | 处理类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 商机开发] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 针对网站上生成的每个商机，允许您上载有关这些商机结果的信息，包括生成的实际收入。在将收入与商机 ID 精确地关联后，即可确定利润率最高的推广和促销活动。 |
| [!UICONTROL 在线报价] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 针对网站上生成的每个商机，允许您上载有关这些商机结果的信息，包括生成的实际收入。在将收入与商机 ID 精确地关联后，即可确定利润率最高的推广和促销活动。 |
| [!UICONTROL 呼叫中心的数据] | [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | 允许您上载呼叫中心交易，以便确定哪些策略（推广活动、促销活动等）会引导客户拨打订购电话。 |
