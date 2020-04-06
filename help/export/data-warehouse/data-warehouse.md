---
description: 数据仓库是指Analytics数据的副本，用于存储和自定义报告，您可以通过筛选数据来运行它。 您可以请求报告，以根据您的独特问题显示原始数据的高级数据关系。 数据仓库报表通过电子邮件发送或通过FTP发送，处理时间最长为72小时。 处理时间取决于查询的复杂性和请求的数据量。
title: Data Warehouse 概述
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Warehouse 概述

数据仓库是指Analytics数据的副本，用于存储和自定义报告，您可以通过筛选数据来运行这些数据。 您可以请求报告，以根据您的独特问题显示原始数据的高级数据关系。 数据仓库报表通过电子邮件发送或通过FTP发送，处理时间最长为72小时。 处理时间取决于查询的复杂性和请求的数据量。

Adobe仅为管理员级别的用户（针对特定报表包）启用数据仓库。 （可以为全局和子报表包启用它，但不能为汇总报表包启用它。）管理员可以创建有权访问数据仓库的用户组，然后将非管理员级别的用户关联到该用户组。

Data Warehouse会自动将任何大小超过1 MB的文件压缩为zip文件。 电子邮件附件的最大大小为10 MB。

数据仓库可以在单个请求中处理不限数量的行，以处理单个计划和下载的报表。

>[!NOTE]Data Warehouse 会报告在报表时段遇到的第一个值。

>[!IMPORTANT]
>
>在对分类的值进行分段时，Analysis Workspace 和 Data Warehouse 处理“未指定”值的方式有所不同。Workspace 中的“未指定”是指未分类的值，而 Data Warehouse 中的“未指定”是指您分类为“未指定”的值。

## Data Warehouse 请求描述 {#section_F21C78ED36884C389C852E876AF5CDE8}

此表介绍了选项卡上的字段和 [!UICONTROL Data Warehouse Request] 选项。

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 请求名称</span> </td> 
   <td colname="col2"> 标识请求。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 报告日期</span> </td> 
   <td colname="col2"> <p>请求的日期和粒度。 </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle">自定义</span>：在日历中配置的日期范围。 </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle">预设</span>：预设范围。预设范围与报表日期相关。 </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle">粒度</span>：时间粒度。有效值为无、小时、天、周、月、季和年。 </li> 
    </ul> <p>虚拟报表包上的数据仓库报告支持在虚拟报表包上配置的备用时区。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 可用区段</span> </td> 
   <td colname="col2"> <p>允许您选择要检查和生成复杂区段的访客群体部分。 您可以加载预配置的区段、创建新区段并将区段组件存储在库中以用于构建其他区段。 </p> <p>您现在可以堆叠区段。 选择多个区段时，预览区域、请求管理器和请求详细信息弹出窗口将显示以逗号分隔的名称列表（例如，区段1、区段2）。 </p> <p>有关详细信息，请参阅<a href="/help/components/c-segmentation/seg-home.md">分段指南</a>。 </p> <p>注意：您不能在同一个 Data Warehouse 报表的同一个区段中既包括区段过滤器，又包括划分。这样做会导致出错。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 划分</span> </td> 
   <td colname="col2"> <p>允许您使用细分对数据分类。 区段和细分的区别在于，区段从数据集中过滤器数据，而细分将细分的所有有效值中的数据划分开来。 </p> 您还可以按一个或多个区段对报表进行细分。 但是，您不能在同一数据仓库报表中同时包含同一区段的区段过滤器和细分。 这样做会导致出错。 <p> 例如，使用区段从数据集中删除性别，并使用细分查看按性别划分的数据。 </p> <p>当提交具有多个多值维度（例如，各种移动报表）的数据仓库请求时，一次点击可以生成指数数的行数。 一次点击可输出的行数上限为100（以前为1,000）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 量度</span> </td> 
   <td colname="col2">允许您添加要报告的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 量度排序</span> </td> 
   <td colname="col2">提供排名的划分报表（按量度值从大到小排序），这与“Reports &amp; Analytics”用户界面、Data Workbench 等的显示情况类似。<a href="/help/export/data-warehouse/sorting-by-metric.md"  > 更多...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 计划提交</span> </td> 
   <td colname="col2"> <p>允许您按选定的间隔计划自动投放请求，或将请求作为一次性报告。 如果使用默认格式，则报告将以。csv文件形式通过电子邮件发送。 </p> <p>若要添加日期范围，请在文件名中包含 <span class="filepath">%R</span>。这个值代表报表中请求的日期值。例如，如果您请求获得从 2013 年 5 月 1 日到 2013 年 5 月 7 日的数据，则 <span class="filepath">%R</span> 显示包含 20130501 - 20130507 日期范围的文件名。 </p> </td> 
  </tr> 
 </tbody> 
</table>

