---
description: 有关 Adobe 如何提供数据源访问权限的信息。
subtopic: Data sources
title: 数据源工作原理
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 数据源工作原理

有关 Adobe 如何提供数据源访问权限的信息。

>[!NOTE] 在经由数据源提交之后，导入的数据便与使用其他方法（JavaScript 信标、ActionSource、数据插入 API 等）收集的报表数据没有区别。导入数据后，便无法删除该数据。

![](assets/data_sources_overview.png)

提交数据有两种方法：

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

您可以通过市场营销报告创建和管理基于FTP的数据源，这些数据源使用FTP文件传输将数据文件导入数据源。 创建数据源后，Adobe会为您提供一个FTP位置，供您上传数据源文件。 上传后，数据源会自动定位和处理它们。 处理后，这些数据便可用于市场营销报告。

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe优惠Data Sources API，它允许您通过编程方式将应用程序链接到数据源。 这消除了对中间FTP服务器的需求，并通过HTTP、SOAP和REST传输数据。

请参 [阅数据源API文档](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)。
