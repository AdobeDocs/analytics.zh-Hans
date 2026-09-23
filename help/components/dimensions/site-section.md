---
title: 网站区域
description: 网站区域的名称。
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 66%
---
# 网站区域

“网站区域”[维度](overview.md)列出了您网站上的网站区域的名称。 对于大型网站，将页面分组到区域会很有帮助。 此维度对于查看“查看次数最多”或“性能最高”网站区域很有帮助。

此维度与[页面](page.md)维度和[服务器](server.md)维度相关。 页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

AppMeasurement 使用 [`channel`](/help/implement/vars/page-vars/channel.md) 变量收集此数据。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`channel`](/help/implement/vars/page-vars/channel.md) |
| **Web SDK / XDM字段** | [`web.webPageDetails.siteSection`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/data-types/webpage-details) |
| **查询参数** | [`ch`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<channel>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

维度项包括您网站上的网站区域名称。 贵组织会确定您要使用的具体维度项目。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
