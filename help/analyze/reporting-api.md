---
description: Reporting API 的资源和链接。
title: Analytics 报表 API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 90%

---

# Analytics 报表 API

Adobe Analytics API 的相关文档位于 [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/) 上。

## 比较各个 Analytics API

| **API 类型** | **完全处理** | **实时** | **实时流** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **描述** | 所有 Analytics 界面中可用的完全处理的完成数据。 | 收集时间段（秒）内可用的部分处理的有限指标。 | 收集时间段（秒）内可用的部分处理的点击数据。 | 用于提取大型数据导出的完全处理的完成数据。 |
| [**延迟**](/help/technotes/latency.md) | 30-90 分钟 | 数秒 — 10 分钟 | 数秒 — 10 分钟 | 90 分钟以上 |
| **处理完成** | 完全 | 部分 | 部分 | 完全 |
| **报告界面** | Analysis Workspace、Report Builder、API | Report Builder 1.4 API中的实时报表 | 仅限 API | Data Warehouse、API |
| **数据粒度** | 汇总 | 汇总 | 点击级别 | 汇总 |
| **访客个人资料处理** | 是 | 否 | 否 | 是 |
| **区段支持** | 是 | 否 | 否 | 部分 |
