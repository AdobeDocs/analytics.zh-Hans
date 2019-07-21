---
description: 本节介绍数据馈送提交中包含的文件。
keywords: 数据馈送；工作；内容；清单；文件；查找；点击数据；交付内容
seo-description: 本节介绍数据馈送提交中包含的文件。
seo-title: 数据源内容-概述
solution: Analytics
subtopic: 数据馈送
title: 数据源内容-概述
topic: Reports & Analytics
uuid: 82a86314-4841-4133-a0 dc-4e7 c6 cd14 fc1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# 数据源内容-概述

本节介绍数据馈送提交中包含的文件。

## 清单文件 {#section_044BBDE2906D49518F8264CD4832D429}

清单文件包含以下有关上载数据集中每个文件的详细信息：

* 文件名
* 文件大小
* MD5 散列
* 文件中包含的记录数

清单文件遵循与 Java JAR 清单文件相同的格式。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. 清单文件根据以下规则命名：

```
<report_suite_id>_YYYY_MM_DD.txt
```

典型的清单文件包含如下类似数据：

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

每个清单文件包含一个标题，指示对照文件、数据文件的总数，以及所有数据文件中的记录总数。此标题后跟多个部分，其中包含数据馈送提交中包括的每个文件的信息。

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 对照文件 {#section_B5863537A48D47D78D0F7274838923C1}

对照文件不包含点击数据，它们是用于提供点击数据列标题的补充文件，以及用于将数据馈送中存在的 ID 转换为实际值的对照文件。例如，浏览器列中的值“497”表示该点击来自“Microsoft Internet Explorer 8”。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. 其他文件（例如 `browser.tsv`）则是通用的。

对照文件在根据以下规则命名的压缩 zip 文件中一同提交：

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
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

## 点击数据文件 {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. 此文件中的数据量由提交格式（每小时或每日、单个或多个文件）确定。此文件仅包含点击数据。列标题与对照文件分开提交。此文件中的每行均包含一个服务器调用。

## 提交内容 {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>文件使用ISO-8859-1进行编码。

根据您所配置的数据馈送类型，Adobe 提交的实际文件会有所不同。请在下面的提交文件说明表中，查找与您的数据馈送匹配的配置。

文件名中指示的时间 (HHMMSS) 总是表示文件所含数据对应的日期范围开始时间，无论文件何时生成或上载。

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 提交格式 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 每日，单个文件 </td> 
   <td colname="col2"> <p>收集一天的数据后，您将收到包含以下内容的提交： </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">单个压缩数据文件。 </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">清单文件。 </li> 
    </ul> <p>数据文件使用以下名称进行提交： </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中，<code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取后，数据文件包含单个 <span class="filepath">hit_data.tsv</span> 文件（含有该日期的所有数据），以及上述压缩对照文件。 </p> <p>根据报表包中的当前使用变量数和流量，点击数据文件大小会有很大差异。但是，一行数据平均约为 500 B（压缩）或 2 KB（未压缩）。将此值乘以服务器调用数，即可粗略估计数据馈送文件的大小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每日，多个文件 </td> 
   <td colname="col2"> <p>收集一天的数据后，您将收到包含以下内容的提交： </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">一个或多个压缩数据文件，分为 2 GB 数据块。 </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">清单文件。 </li> 
    </ul> <p>每个数据文件使用以下名称进行提交： </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中，<code>&lt;index&gt;</code> 是从 <i>1</i> 到 <i>n</i> 增加的文件索引（假设有 <i>n</i> 个文件），而 <code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取后，每个数据文件包含单个 <span class="filepath">hit_data.tsv</span>（含有大约 2 GB 的解压缩数据），以及上述压缩对照文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小时，单个文件 </td> 
   <td colname="col2"> <p>收集一小时的数据后，您将收到包含以下内容的提交： </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">单个数据文件。 </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">清单文件。 </li> 
    </ul> <p>数据文件使用以下名称进行提交： </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;-&lt; HHMMSS&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中，<code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取后，数据文件包含单个 <span class="filepath">hit_data.tsv</span> 文件，其中含有该小时的所有数据。上述压缩对照文件仅与每天第一个小时的数据一同提交。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小时，多个文件 </td> 
   <td colname="col2"> <p>收集一小时的数据后，您将收到包含以下内容的提交： </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">一个或多个压缩数据文件，分为 2 GB 数据块。 </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">清单文件。 </li> 
    </ul> <p>每个数据文件使用以下名称进行提交： </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;-&lt; HHMMSS&gt;. tsv。&lt;compression_suffix&gt;
    </code> <p>其中，<code>&lt;index&gt;</code> 是从 <i>1</i> 到 <i>n</i> 增加的文件索引（假设有 <i>n</i> 个文件），而 <code>&lt;compression_suffix&gt;</code> 是 <code>gz</code> 或 <code>zip</code>。 </p> <p>提取后，每个数据文件包含单个 <span class="filepath">hit_data.tsv</span>，其中含有大约 2 GB 的解压缩数据。上述压缩对照文件仅与每天第一个小时的数据一同提交。 </p> </td> 
  </tr> 
 </tbody> 
</table>

