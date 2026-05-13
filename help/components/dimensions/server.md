---
title: 服务器
description: 服务器的名称。
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 92%

---

# 服务器

“服务器”[维度](overview.md)通常列出网站的主机名。 对于组合多个域或子域的报表包，当想要了解哪些域或子域的性能最佳时，此维度很有价值。

此维度与[页面](page.md)维度和[网站区域](site-section.md)维度相关。 页面粒度最大，服务器粒度最小，网站区域介于两者之间。

## 使用数据填充此维度

此维度从图像请求中的 [`server` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 AppMeasurement 使用 [`server`](/help/implement/vars/page-vars/server.md) 变量收集此数据。

## 维度项目

维度项目包括您网站上的服务器。 贵组织会确定您要使用的具体维度项目。 有些组织使用 `window.location.hostname`，而另一些组织则制定自定义值。 无论您使用哪种方法，都应确保其一致性，并记录在[解决方案设计文档](/help/implement/prepare/solution-design.md)中。
