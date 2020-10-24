---
description: 有关数据源模板的信息，该模板提供了一个数据框架，可用于将一组特定的外部数据提交到数据源。
subtopic: Data sources
title: 数据源模板概述
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '247'
ht-degree: 100%

---


# 数据源模板概述

有关数据源模板的信息，该模板提供了一个数据框架，可用于将一组特定的外部数据提交到数据源。

由该向导生成的模板文件旨在让您初步掌握导入。模板中定义的列不受限制。您可以根据需要任意添加其他列，只要对应所选数据处理类型的量度或定义受到支持即可。

您可以在以下各节中查看每种类型有哪些受支持的量度和维度：

* [网络日志](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)（不再受支持）
* [转化](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [访客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [完全处理](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

例如，对于访客 ID 数据类型，您可以为[访客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md) 中列出的任何量度或维度添加一列。

创建模板之后，您就可以下载它并导入您的数据，然后将数据上载到数据源 FTP 站点。在经数据源服务器处理之后，导入的数据即可用于您的市场营销报表。

数据源模板是一个 [!DNL .txt] 文件，可使用任何文本编辑器将其打开。但是，模板最简单的处理方式是使用 Microsoft Excel 或其他电子表格应用程序。模板内容会根据您在[!UICONTROL 数据源激活向导]中的选择而改变。

请参阅[导入文件引用](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)以了解更多详细信息。
