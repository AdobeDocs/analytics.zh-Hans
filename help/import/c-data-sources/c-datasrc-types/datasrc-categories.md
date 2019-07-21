---
description: 数据源类别可识别具有相似功能的不同数据源类型。
seo-description: 数据源类别可识别具有相似功能的不同数据源类型。
seo-title: 数据类型和类别概述
solution: Analytics
subtopic: 数据源
title: 数据类型和类别概述
topic: 开发人员和实施
uuid: b5004cdc-b68 a-4a82-a152-a157-a7 cd7 b8 bfe21
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# 数据类型和类别概述

数据源类别可识别具有相似功能的不同数据源类型。

通过类别，可以从用户的角度对数据源进行分组。通过数据源 UI 创建数据源时，首先要选择一个数据源类别，然后选择一个特定的数据源类型。每个类别都包含多种支持相似数据类型的数据源类型。数据源具有以下数据源类别：

## 网站使用 {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>网站服务器日志文件 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B" type="concept" format="dita" scope="local"> 网络日志 </a> </p> </td> 
   <td colname="col3"> <p>大多数网站服务器都会生成日志文件，其中记录了所提供的每一个页面。使用该数据源，您可以处理来自大多数网站服务器数据的日志文件，并将该数据添加到您的报表中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Cloud批量上传 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>在Advertising Cloud中提供手动和Excel自动批量上传。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>站点级别流量数据源 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> 流量 </a> </p> </td> 
   <td colname="col3"> <p>导入整个网站的流量数据。例如，页面查看次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>划分流量数据源 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC" type="concept" format="dita" scope="local"> 流量 </a> </p> </td> 
   <td colname="col3"> <p>导入由其他网站变量划分的流量数据。例如，按产品划分的页面查看次数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 广告活动 {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>通用广告服务器 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将涉及广告服务器上的广告服务活动的显示次数及其他首要量度集成到市场营销报表中。该数据源是通用的广告服务器数据源，如果您的特定广告服务器不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通用电子邮件促销活动服务器 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将电子邮件促销活动服务器中的量度集成到市场营销报表中。 </p> <p>通常合成量度包括已发送、已递送和已阅读邮件的数量。该数据源是通用的电子邮件促销活动数据源，如果您的特定电子邮件促销活动服务器不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每次点击付费一般服务 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p> 允许您导入有关每次点击付费绩效（包括显示次数、点击量和成本）的数据。 </p> <p>该数据源是通用的每次点击付费数据源，如果您的特定每次点击付费服务不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 客户关系管理 (CRM) {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>通用呼叫中心 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将有关呼叫中心的信息集成到市场营销报表中。通常导入的量度包括呼叫次数、通话时间、代理商和销售总额。 </p> <p>该数据源是通用的呼叫中心数据源，如果您的特定呼叫中心软件不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>通用客户支持 </p> <p>应用程序 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将客户支持软件中的信息集成到市场营销报表中。它包括某些量度，如新事件的数量、已解决事件的数量和解决事件所花费的时间。 </p> <p>该数据源是通用的客户支持数据源，如果您的特定客户服务应用程序不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 客户满意度 {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>普通调查数据 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将来自第三方工具的调查结果集成到市场营销报表中，并通过客户与您的网站之间的交互情况显示客户的满意度。 </p> <p>该数据源是通用调查数据源，如果您的特定调查数据服务不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 网站性能 {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>普通网站下载速度 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您将来自跟踪下载速度的应用程序或服务的数据集成到您的数据。 </p> <p>该数据源是通用下载速度数据源，如果您的特定下载速度软件或服务不在支持之列，应使用该数据源。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 通用 {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>普通数据源（仅限概要数据） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>如果没有数据源更匹配要导入市场营销报告与分析的数据类型，则使用该数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>普通数据源（完全处理） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> 完全处理 </a> </p> </td> 
   <td colname="col3"> <p>允许您导入日志文件数据。对该数据的处理就好像是由数据收集服务器在指定时间接收到它（每次点击都会收到一个时间戳）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>普通数据源（交易 ID） </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776" type="concept" format="dita" scope="local"> 交易 ID </a> </p> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5" type="concept" format="dita" scope="local"> Visitor ID </a> </p> </td> 
   <td colname="col3"> <p>允许您将任何离线事件绑定到在线事件。交易 ID 可作为离线和在线事件之间的键。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 在线购买 {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>退货 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您导入退货数据，并将其与购买 ID 关联，这样您就可以确定搜索引擎、关键词、营销活动及其他更有可能产生退货的属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>产品成本 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您提供从您的网站购买和发出的产品的实际成本。将成本或利润与单个产品相关联后，即可精确地报告网站中利润率最高的促销活动、关键词和内部促销活动。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>订购状态 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您使用量度确认每个订购的状态，包括被取消、已发货、已完成或属欺诈行为的订购。 </p> <p>订购状态报告功能可以确定哪些赢取方法产生的订购完成率最高。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 商机和报价 {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据源 </p> </th> 
   <th colname="col2" class="entry"> <p>处理类型 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>推介发生 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>针对网站上生成的每个商机，允许您上载有关这些商机结果的信息，包括生成的实际收入。 </p> <p>在将收入与商机 ID 精确地关联后，即可确定利润率最高的推广和促销活动。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在线报价 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>针对网站上生成的每个商机，允许您上载有关这些商机结果的信息，包括生成的实际收入。 </p> <p>在将收入与商机 ID 精确地关联后，即可确定利润率最高的推广和促销活动。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>呼叫中心的数据 </p> </td> 
   <td colname="col2"> <p> <a href="../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0" type="concept" format="dita" scope="local"> 转化 </a> </p> </td> 
   <td colname="col3"> <p>允许您上载呼叫中心交易，以便确定哪些策略（推广活动、促销活动等）会引导客户拨打订购电话。 </p> </td> 
  </tr> 
 </tbody> 
</table>

