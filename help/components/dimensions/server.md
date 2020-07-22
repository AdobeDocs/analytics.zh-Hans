---
title: Server
description: 服务器的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# Server

“服务器”维通常列表站点的主机名。 对于组合多个域或子域的报表包，此维对于查看哪些域或子域的性能最佳非常有用。

此维与“页面”和“ [站点](page.md) ” [部分维相关](site-section.md) 。 页面粒度最细，服务器粒度最细，站点部分介于两者之间。

## 用数据填充此维

此维从图像请求中的 [`server` 查询字符串](/help/implement/validate/query-parameters.md) 检索数据。 AppMeasurement使用变量收集此 [`server`](/help/implement/vars/page-vars/server.md) 数据。

## 维项

维项目包括站点上的服务器。 您的组织确定要使用哪些特定维项目。 一些组织使 `window.location.hostname`用，而另一些组织使用自定义值。 无论您使用何种方法，都应确保其一致性，并将其记录在解决方案 [设计文档中](/help/implement/prepare/solution-design.md)。
