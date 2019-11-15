---
description: 本节介绍数据馈送提交中包含的文件。
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
solution: Analytics
subtopic: data feeds
title: 数据馈送内容 - 概述
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 数据馈送内容 - 概述

本节介绍数据馈送提交中包含的文件。

## 清单文件

清单文件包含以下有关上载数据集中每个文件的详细信息：

* 文件名
* 文件大小
* MD5 散列
* 文件中包含的记录数

清单文件遵循与 Java JAR 清单文件相同的格式。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. 清单文件根据以下规则命名：

```text
[rsid]_[YYYY-mm-dd].txt
```

典型的清单文件包含如下类似数据：

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

每个清单文件包含一个标题，指示对照文件、数据文件的总数，以及所有数据文件中的记录总数。此标题后跟多个部分，其中包含数据馈送提交中包括的每个文件的信息。

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 查找文件

某些数据馈送列输出一个与其实际值相对应的数字。 查找文件用于匹配数据馈送列中的数字，并将其与实际值匹配。 例如，点击数据列中的值为“497” `browser` 表示点击来自“Microsoft Internet Explorer 8”（如果您查看） `browser.tsv`。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. 其他文件（例如 `browser.tsv`）则是通用的。

对照文件在根据以下规则命名的压缩 zip 文件中一同提交：

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* [!DNL column_headers.tsv]（针对此数据馈送自定义的规则）
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv]（针对此数据馈送自定义的规则）

## 点击数据文件

Hit data is provided in a [!DNL hit_data.tsv] file. 此文件中的数据量由提交格式（每小时或每日、单个或多个文件）确定。此文件仅包含点击数据。列标题与对照文件分开提交。此文件中的每行均包含一个服务器调用。

Adobe交付的文件因您配置的数据源类型而异。 所有文件都使用ISO-8859-1进行编码。

* `[rsid]` 引用数据源所来自的报表包ID。
* `[index]` 仅用于多个文件源，并引用分页文件的正确顺序。
* `[YYYY-mm-dd]` 指数据馈送的开始日期。
* `[HHMMSS]` 仅在每小时馈送中使用，并引用数据馈送的起始小时数。
* `[compression_suffix]` 指使用的压缩类型。 通常，数据馈送会压缩到 `tar.gz` 或文 `zip` 件中。

### 每日，单个文件

在收集一天的数据后，您将收到一个压缩数据文件和一个清单文件。 数据文件名为：

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，数据文件包含一个包含当 `hit_data.tsv` 天所有数据的文件，以及任何所需列的查找文件。

### 每天，多个文件

在收集一天的数据后，您将收到一个或多个压缩数据文件和清单文件。 数据文件名为：

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，每个数据文件都包含一个包含约2GB `hit_data.tsv` 未压缩数据的文件，以及任何所需列的查找文件。

### 每小时，单个文件

在收集数据一小时后，您将收到单个压缩数据文件和清单文件。 数据文件名为：

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取后，数据文件包含一个包含该小 `hit_data.tsv` 时所有数据的文件，以及任何所需列的查找文件。

### 每小时，多个文件

在收集数据一小时后，您将收到一个或多个压缩数据文件和清单文件。 数据文件名为：

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取后，每个数据文件都包含一个包含约2GB `hit_data.tsv` 未压缩数据的文件，以及任何所需列的查找文件。

## 数据文件大小

点击数据文件的大小根据当前使用的变量数和发送到报表包的流量而有很大不同。 但是，一行数据平均约为 500 B（压缩）或 2 KB（未压缩）。将其乘以服务器调用数，可以粗略估计数据馈送文件的大小。 在您的组织开始接收数据馈送文件后，您可以通过将行数除以其总文件大小来找到更 `hit_data.tsv` 准确的数字。
