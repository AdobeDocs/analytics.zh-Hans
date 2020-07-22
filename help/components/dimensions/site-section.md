---
title: 站点部分
description: 站点部分的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# 站点部分

“站点部分”维列表站点上站点部分的名称。 对于大型网站，将页面分组到各个部分会很有帮助。 此维度有助于查看查看次数最多或效果最佳的站点部分。

此维与页面和服 [务器](page.md) 维 [相关](server.md) 。 页面粒度最细，服务器粒度最细，站点部分介于两者之间。

## 用数据填充此维

此维从图像请求中的 [`ch` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 [`channel`](/help/implement/vars/page-vars/channel.md) 数据。

## 维项

维项目包括站点上站点部分的名称。 您的组织确定要使用哪些特定维项目。 无论您使用何种方法，都应确保其一致性，并将其记录在解决方案 [设计文档中](/help/implement/prepare/solution-design.md)。
