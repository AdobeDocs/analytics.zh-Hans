---
description: 有关 Adobe 如何提供数据源访问权限的信息。
subtopic: Data sources
title: 数据源工作原理
topic-fix: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
exl-id: 3d56ca3f-6c45-48d0-bbd2-53d6babfbb83
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 100%

---

# 数据源工作原理

有关 Adobe 如何提供数据源访问权限的信息。

>[!NOTE]
>
>在经由数据源提交之后，导入的数据便与使用其他方法（JavaScript 信标、ActionSource、数据插入 API 等）收集的报表数据没有区别。数据一经导入便无法删除。

![](assets/data_sources_overview.png)

可使用以下两种方法来提交数据：

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

您可以通过市场营销报表创建和管理基于 FTP 的数据源，它可使用 FTP 文件传输将数据文件导入数据源。在创建数据源之后，Adobe 会为您提供一个 FTP 位置，可供您上载数据源文件。上载完成之后，数据源可自动查找并处理这些数据源文件。处理完成之后，相关数据即可用于市场营销报表。

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe 提供的数据源 API，可让您以编程方式将自己的应用程序链接到数据源。这种方式不再需要中间 FTP 服务器，也不需要经由 HTTP、SOAP 和 REST 传输数据。

请参阅[数据源 API 文档](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)。
