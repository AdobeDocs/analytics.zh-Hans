---
description: Reporting API 的资源和链接。
title: Analytics 报表 API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 73%

---

# Analytics 报表 API

有关Adobe Analytics API的文档位于[Adobe I/O](https://adobe.io/analytics-apis/docs)上。

## Analytics API比较

| **API 类型** | **完全处理** | **实时** | **实时流** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **描述** | 所有 Analytics 界面中可用的完全处理的完成数据。 | 收集时间段（秒）内可用的部分处理的有限量度。 | 收集时间段（秒）内可用的部分处理的点击数据。 | 用于提取大型数据导出的完全处理的完成数据。 |
| [**延迟**](/help/technotes/latency.md) | 30-90 分钟 | 数秒 - 10 分钟 | 数秒 - 10 分钟 | 90分钟以上 |
| **处理完成** | 完全 | 部分 | 部分 | 完全 |
| **报表界面** | Analysis Workspace、Reports &amp; Analytics、Report Builder、API | Reports &amp; Analytics、Report Builder、1.4 API中的实时报表 | 仅限 API | data warehouse, API |
| **数据粒度** | 汇总 | 汇总 | 点击级别 | 汇总 |
| **访客资料处理** | 是 | 否 | 否 | 是 |
| **区段支持** | 是 | 否 | 否 | 部分 |