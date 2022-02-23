---
title: 批量数据插入 API
description: 批量数据插入API(BDIA)是一项Adobe Analytics功能，它允许您批量上传文件中的服务器调用数据，而不是使用客户端库（如AppMeasurement）。 这些批处理文件中的服务器调用可以是当前（实时）数据或历史数据。 它是Adobe Analytics API早期版本中数据插入API的更具扩展性的后继版本。
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---


# 批量数据插入 API

Bulk Data Insertion可解决多个用例，例如：

* 从以前的分析系统中摄取历史数据

* 一个内部分析收集系统，它使得使用AppMeasurement变得不可行。 您可以使用提取 — 转换加载(ETL)流程将数据放入批处理文件中，然后使用BDIA将数据上传到Adobe Analytics。

* 从只间歇性连接到Internet的设备收集数据。 这些设备会存储交互，直到它们收到连接为止。 然后，设备可以通过BDIA一次全部上传数据。

数据插入API和 [批量数据插入API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)是将服务器端收集数据提交到Adobe Analytics的两种方法。 每次生成事件时都将调用“数据插入 API”。“批量数据插入 API”接受包含事件数据在内的 CSV 格式的文件，其中每行有一个事件。如果您正在实施新的服务器端收集，我们建议您使用“批量数据插入 API”。