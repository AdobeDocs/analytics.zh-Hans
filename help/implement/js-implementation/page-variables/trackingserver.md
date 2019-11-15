---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# trackingServer

 变量用于第一方 Cookie 实施，以指定写入图像请求和 Cookie 的域名。

<!-- 

trackingServer.xml

 -->

用于非安全页面。如果&#x200B;*`trackingServer`*&#x200B;已定义，则无任何数据发送至 2o7.net。如果未定义 *`trackingServer`*（且未定义 dc），则数据将发送至 112.2o7.net。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | "" |

可在[此处](https://helpx.adobe.com/analytics/kb/determining-data-center.html)查找 Adobe 数据中心列表。