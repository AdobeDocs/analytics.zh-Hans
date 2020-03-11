---
description: 本节介绍数据馈送提交中包含的文件。
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: 数据馈送内容 - 概述
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

清单文件总是作为单独的 `.txt` 文件最后提交，因此如果存在清单文件，则表示已经提交了该请求时段的完整数据集。清单文件根据以下规则命名：

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

一些馈送配置为接收 `.fin` 文件，而不是 `.txt` 清单。`.fin` 表示上传完成，但是不包含有关上传的元数据。

## 查询文件

某些数据馈送列会输出一个与其实际值相对应的数字。查询文件用于匹配数据馈送列中的数字，并将其与实际值匹配。例如，如果您查看 `browser.tsv`，`browser` 点击数据列中的值“497”表示点击来自“Microsoft Internet Explorer 8”。

请注意，`column_headers.tsv` 和 `event_list.tsv` 特定于数据馈送和报表包。其他文件（例如 `browser.tsv`）则是通用的。

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

点击数据在 [!DNL hit_data.tsv] 文件中提供。此文件中的数据量由提交格式（每小时或每日、单个或多个文件）确定。此文件仅包含点击数据。列标题与对照文件分开提交。此文件中的每行均包含一个服务器调用。

根据您所配置的数据馈送类型，Adobe 提交的文件会有所不同。所有文件都使用 ISO-8859-1 进行编码。

* `[rsid]` 是指作为数据馈送来源的报表包 ID。
* `[index]` 仅用于多文件馈送，它是指分页文件的正确顺序。
* `[YYYY-mm-dd]` 是指数据馈送的开始日期。
* `[HHMMSS]` 仅用于每小时馈送，它是指数据馈送的起始时间（小时）。
* `[compression_suffix]` 是指使用的压缩类型。通常，数据馈送会压缩为 `tar.gz` 或 `zip` 文件。

### 每日，单个文件

在收集了某天的数据后，您将收到一个压缩的数据文件以及一个清单文件。数据文件名为：

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，数据文件包含一个含有当天所有数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

### 每天，多个文件

在收集了某天的数据后，您将收到一个或多个压缩的数据文件以及一个清单文件。数据文件名为：

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，每个数据文件都包含一个含有约 2GB 未压缩数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

### 每小时，单个文件

在收集了某一小时的数据后，您将收到一个压缩的数据文件以及一个清单文件。数据文件名为：

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取后，数据文件包含一个含有那一小时内所有数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

### 每小时，多个文件

在收集了某小时的数据后，您将收到一个或多个压缩的数据文件以及一个清单文件。数据文件名为：

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取后，每个数据文件都包含一个含有约 2GB 未压缩数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

## 数据文件大小

根据当前使用的变量数量和发送到报表包的流量，点击数据文件大小会有很大差异。但是，一行数据平均约为 500 B（压缩）或 2 KB（未压缩）。将此值乘以服务器调用数，即可粗略估计数据馈送文件的大小。在您的组织开始接收数据馈送文件后，您可以通过使用 `hit_data.tsv` 中的行数除以其总文件大小，得到更准确的数字。
