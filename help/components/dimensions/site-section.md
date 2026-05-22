---
title: 网站区域
description: 网站区域的名称。
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 90%

---

# 网站区域

“网站区域”[维度](overview.md)列出了您网站上的网站区域的名称。 对于大型网站，将页面分组到区域会很有帮助。 此维度对于查看“查看次数最多”或“性能最高”网站区域很有帮助。

此维度与[页面](page.md)维度和[服务器](server.md)维度相关。 页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`ch` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 AppMeasurement 使用 [`channel`](/help/implement/vars/page-vars/channel.md) 变量收集此数据。

## 维度项目

维度项目包括您网站上的网站区域的名称。 贵组织会确定您要使用的具体维度项目。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
