---
description: 本节介绍数据馈送提交中包含的文件。
keywords: 数据馈送;作业;内容;清单;文件;查找;点击数据;交付内容
subtopic: data feeds
title: 数据馈送内容 - 概述
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 100%

---

# 数据馈送内容 - 概述

以下几个部分介绍了如何访问和理解数据馈送传递中的文件。

## 访问数据馈送内容

要访问数据馈送的内容：

1. 登录到数据馈送目标网站。

   这是您在创建数据馈送时设置的目标网站，例如 Amazon S3 或 Google Cloud Platform 存储桶。

1. 将压缩的数据馈送文件下载到本地计算机。

1. 使用支持 `.tar.gz` 文件扩展名的程序解压已压缩文件。

1. 在您选择的电子表格或数据库应用程序中打开 `hit_data.tsv` 文件，以查看当天的原始数据。-->

## 清单文件 {#feed-manifest}

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

典型的清单文件包含类似这样的数据：

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

每个清单文件包含一个标题，注明查找文件、数据文件的总数，以及所有数据文件中的记录总数。此标题后面有多个部分，其中包含数据馈送传递中包括的每个文件的信息。

一些馈送配置为接收 `.fin` 文件，而不是 `.txt` 清单。`.fin` 表示上传完成，但其中包含的元数据采用旧格式。

## 查询文件

某些数据馈送列会输出一个与其实际值相对应的数字。查询文件用于匹配数据馈送列中的数字，并将其与实际值匹配。例如，如果您查看 `browser.tsv`，`browser` 点击数据列中的值“497”表示点击来自“Microsoft Internet Explorer 8”。

请注意，`column_headers.tsv` 和 `event_list.tsv` 特定于数据馈送和报表包。其他文件（例如 `browser.tsv`）则是通用的。

对照文件在根据以下规则命名的压缩 zip 文件中一同提交：

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**：包含 `hit_data.tsv` 的列标题的一行。
* **`browser.tsv`**：将浏览器 ID（`browser` 馈送列）映射到浏览器的友好名称。
* **`browser_type.tsv`**：将浏览器 ID（`browser` 馈送列）映射到浏览器类型。
* **`color_depth.tsv`**：将颜色深度 ID（`color` 馈送列）映射到颜色深度。
* **`connection_type.tsv`**：将连接类型 ID（`connection_type` 馈送列）映射到连接类型。
* **`country.tsv`**：将国家/地区 ID（`country` 馈送列）映射到国家/地区名称。
* **`javascript_version.tsv`**：将 JavaScript 版本 ID（`javascript` 馈送列）映射到 JavaScript 版本。
* **`languages.tsv`**：将语言 ID（`language` 馈送列）映射到语言。
* **`operating_systems.tsv`**：将操作系统 ID（`os` 馈送列）映射到操作系统名称。
* **`plugins.tsv`**：将插件 ID（`plugin` 馈送列）映射到每个相应的插件名称。
* **`resolution.tsv`**：将分辨率 ID（`resolution` 馈送列）映射到显示器分辨率。
* **`referrer_type.tsv`**：将反向链接类型 ID（`ref_type` 馈送列）映射到反向链接类型。
* **`search_engines.tsv`**：将搜索引擎 ID（`search_engine` 馈送列）映射到搜索引擎名称。
* **`event.tsv`**：将每个事件 ID（`event_list` 馈送列）映射到其相应的事件名称。

## 点击数据文件

点击数据在 `hit_data.tsv` 文件中提供。此文件中的数据量取决于传递格式（每小时或每日，单个或多个文件）。此文件仅包含点击数据。列标题与查找文件分开传输。此文件中的每行均包含一个服务器调用。

根据您所配置的数据馈送类型，Adobe 提交的文件会有所不同。所有文件都使用 ISO-8859-1 进行编码。

* `[rsid]` 是指作为数据馈送来源的报表包 ID。
* `[index]` 仅用于多文件馈送，它是指分页文件的正确顺序。
* `[YYYY-mm-dd]` 是指数据馈送的开始日期。
* `[HHMMSS]` 仅用于每小时馈送，它是指数据馈送的起始时间（小时）。
* `[compression_suffix]` 是指使用的压缩类型。通常，数据馈送会压缩为 `tar.gz` 或 `zip` 文件。
* `[format_suffix]` 是文件格式类型。通常数据馈送文件格式为 `.tsv`。

### 每天，单个文件

在收集了某天的数据后，您将收到一个压缩的数据文件以及一个清单文件。数据文件名为：

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，数据文件包含一个含有当天所有数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

### 每天，多个文件

在收集了某天的数据后，您将收到一个或多个压缩的数据文件以及一个清单文件。数据文件名为：

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取后，每个数据文件都包含一个含有约 2GB 未压缩数据的 `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` 文件，以及任何所需列的查询文件。

### 每小时，单个文件

在收集了某一小时的数据后，您将收到一个压缩的数据文件以及一个清单文件。数据文件名为：

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

提取后，数据文件包含一个含有那一小时内所有数据的 `hit_data.tsv` 文件，以及任何所需列的查询文件。

### 每小时，多个文件

在收集了某小时的数据后，您将收到一个或多个压缩的数据文件以及一个清单文件。数据文件的名称：

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

提取后，每个数据文件都包含一个含有约 2 GB 未压缩数据的 `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]` 文件，以及任何所需列的查找文件。

## 数据文件大小

根据当前使用的变量数量和发送到报表包的流量，点击数据文件大小会有很大差异。但是，一行数据平均约为 500 B（压缩）或 2 KB（未压缩）。将此值乘以服务器调用数，即可粗略估计数据馈送文件的大小。在您的组织开始接收数据馈送文件后，您可以通过使用 `hit_data.tsv` 中的行数除以其总文件大小，得到更准确的数字。