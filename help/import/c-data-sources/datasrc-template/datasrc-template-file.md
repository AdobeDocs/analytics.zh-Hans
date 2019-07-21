---
description: 有关数据源模板的信息，该模板提供了一个数据框架，可用于将一组特定的外部数据提交到数据源。
seo-description: 有关数据源模板的信息，该模板提供了一个数据框架，可用于将一组特定的外部数据提交到数据源。
seo-title: 数据源模板概述
solution: Analytics
subtopic: 数据源
title: 数据源模板概述
topic: 开发人员和实施
uuid: e768bcff-a996-44c7-a7 f2-9a2 c651 ecad9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 数据源模板概述

有关数据源模板的信息，该模板提供了一个数据框架，可用于将一组特定的外部数据提交到数据源。

由该向导生成的模板文件旨在让您初步掌握导入。模板中定义的列不受限制。您可以根据需要任意添加其他列，只要对应所选数据处理类型的量度或定义受到支持即可。

您可以在以下各节中查看每种类型有哪些受支持的量度和维度：

* [网络日志](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [流量](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC)（不再受支持）
* [转化](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [交易 ID](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [完全处理](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

创建模板之后，您就可以下载它并导入您的数据，然后将数据上载到数据源 FTP 站点。在经数据源服务器处理之后，导入的数据即可用于您的市场营销报表。

The Data Source template is a [!DNL .txt] file that you can open with any text editor. 但是，模板最简单的处理方式是使用 Microsoft Excel 或其他电子表格应用程序。模板内容会根据您在[!UICONTROL 数据源激活向导]中的选择而改变。

请参阅[导入文件引用](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD)以了解更多详细信息。
