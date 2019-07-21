---
description: 有关使用数据源之前的报表包要求的信息。
seo-description: 有关使用数据源之前的报表包要求的信息。
seo-title: 要求和上传限制
solution: Analytics
subtopic: 数据源
title: 要求和上传限制
topic: 开发人员和实施
uuid: d79fca77-fa0 e-4171-b978-cdee5 c67 d9 df
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 要求和上传限制

有关使用数据源之前的报表包要求的信息。

以下各节列出了数据源以及导入市场营销报告与分析的数据所适用的限制。

* [大小限制](../../import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [日期](../../import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [常规](../../import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [多字节支持](../../import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [上载网络日志文件](../../import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## 大小限制 {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* 每个 FTP 帐户上所有文件的数据总量不得超过 50 MB。如果数据总量超过 50 MB，处理便会暂停，并且直到数据总量低于 50 MB 时才会恢复。

## 日期 {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* 每一个日历天可上载 90 个唯一日期的数据。如果超过此限制，上载则会失败，并出现错误消息，提示您超过了唯一天数的上限。
* 只能导入具有当前或过去日期的数据。请勿尝试在数据源数据中使用未来日期。
* 所有行必须具有一个指定日期，用于启用报表制图功能。如果某行不包含日期，数据源会生成一个错误并拒绝该文件。日期/时间格式依不同的数据源类型而改变：

   * **完全处理数据源**：使用ISO8601的日期格式( `YYYY-MM-DDThh:mm:ss±UTC_offset` 例如， `2013-09-01T12:00:00-07:00`)或Unix时间格式(自1970年月日起已使用过秒)。

   * **标准和集成数据源**：使用以下日期格式： `MM/DD/YYYY/HH/mm/SS` (例如，)`01/01/2013/06/00/00`

## 常规 {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* 在上载数据源文件时，数据源会执行基本的数据验证，以确保文件不含格式错误。如果某文件中遇到错误，将发送一封电子邮件通知，并停止处理。
* 数据字段不能包含分号。数据源会跳过包含分号的记录。
* 网络日志、流量和某些普通数据源组中的数据在 Data Warehouse 或 Discover 中不可用。For more information, see [Data Types and Categories](../../import/c-data-sources/c-datasrc-types/datasrc-categories.md#concept_42D1534F48324F20B4F9297FC4022105).
* 数据源不支持序列化事件。

## 多字节支持 {#section_96C8D26B21184C3E839865DB6F23EA22}

数据源支持多字节编码。数据源尝试检测传入数据源文件的格式，并会在必要时将其转换为受支持的格式。下表列出了常见字符格式及其支持状态。

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字符格式 </th> 
   <th colname="col2" class="entry"> 支持 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>受支持。与数据源一起使用的报表包必须启用多字节字符支持。 </p> <p>请参阅帮助中的<a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=new_report_suite" format="https" scope="external">新报表包</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 带字节顺序标记的 UTF-8 (EF BB BF) </td> 
   <td colname="col2"> <p>受支持。此格式为非标准格式，虽然许多 Windows 应用程序都以该格式保存。 </p> <p>例如，如果选择“UTF-8”，WordPad 即会以此格式保存。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1（即 Latin-1 或 Windows-1252） </td> 
   <td colname="col2"> 受支持。如果选择“制表符分隔”导出，Microsoft Excel 即以此格式保存。报表包必须使用 ISO-8859-1 区域设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian，带字节顺序标记 (FF FE) </td> 
   <td colname="col2"> 转换为 ISO-8859-1 或 UTF-8，由您的报表包配置确定。如果选择 unicode 导出，Microsoft Excel 即以此格式保存。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian，带字节顺序标记 (EF FF) </td> 
   <td colname="col2"> 转换为 ISO-8859-1 或 UTF-8，由您的报表包配置确定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16，不带字节顺序标记 </td> 
   <td colname="col2"> 不受支持。 </td> 
  </tr> 
 </tbody> 
</table>

如果您提交 UTF-8 或 ISO-8859-1 文件，并且您的报表包配置不支持它，则会发生以下情况之一：

* 转化期间检测到错误，此时您会收到一则类似如下内容的消息：“从 UTF-8 到 ISO-8859-1 转化期间，在位置 18 的文件中发现坏字符”。
* 文件处理过程中未出现错误，但是报表中存在混乱的数据。

## 上载网络日志文件 {#section_DD736FC971FE45C89AB310BEDC1FE707}

* 用于查看网络日志数据的最有用报表是流量报表，如页面查看。
* 页面名称显示为整个 URL，其中包括查询字符串。
* 每个文件请求都显示为一个单独的页面查看，其中包括样式表和图像文件。
* 如果您在 URL 后附加信息，文件可能会被记录为单独的页面。例如，市场营销报表会将以下 URL 记录为两个单独的页面：

[!DNL /jokes/misc/snail_joke.html?userid=12345]

[!DNL /jokes/misc/snail_joke.html?userid=98765]
