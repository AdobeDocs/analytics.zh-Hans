---
title: 站点部分
description: 站点部分的名称。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# 站点部分

“站点部分”维列表站点上站点部分的名称。 对于大型网站，将页面分组到各个部分会很有帮助。 此维度有助于查看查看次数最多或效果最佳的站点部分。

此维与页面和服 [务器](page.md) 维 [相关](server.md) 。 页面粒度最细，服务器粒度最细，站点部分介于两者之间。

## 用数据填充此维

此维从图像请求中的 [`ch` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 [`channel`](/help/implement/vars/page-vars/channel.md) 数据。

## 维值

维值包括站点上站点部分的名称。 您的组织确定您要使用的特定维度值。 无论您使用何种方法，都应确保其一致性，并将其记录在解决方案 [设计文档中](/help/implement/prepare/solution-design.md)。
