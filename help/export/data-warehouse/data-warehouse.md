---
description: Data Warehouse 是指用于存储的 Analytics 数据副本，以及可通过过滤这些数据来运行的自定义报表。您可让报表根据您的特定问题显示原始数据的高级数据关系。Data Warehouse 报表通过电子邮件或 FTP 发送，过程可能需要长达 72 小时。处理时间取决于查询的复杂程度和请求的数据量。
seo-description: Data Warehouse 是指用于存储的 Analytics 数据副本，以及可通过过滤这些数据来运行的自定义报表。您可让报表根据您的特定问题显示原始数据的高级数据关系。Data Warehouse 报表通过电子邮件或 FTP 发送，过程可能需要长达 72 小时。处理时间取决于查询的复杂程度和请求的数据量。
seo-title: 数据仓库概述
solution: Analytics
title: 数据仓库概述
topic: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46 dd6 e1 cd1
translation-type: tm+mt
source-git-commit: 15d49195e5d555adcc37366d679d6b971972504b

---


# 数据仓库概述

Data Warehouse 是指用于存储的 Analytics 数据副本，以及可通过过滤这些数据来运行的自定义报表。您可让报表根据您的特定问题显示原始数据的高级数据关系。Data Warehouse 报表通过电子邮件或 FTP 发送，过程可能需要长达 72 小时。处理时间取决于查询的复杂程度和请求的数据量。

对于特定的报表包，Adobe 仅为管理员级别的用户启用 Data Warehouse。（全局报表包和子报表包均可启用 Data Warehouse，但汇总报表包不可启用。）管理员可创建访问 Data Warehouse 的群组，然后将非管理员级别的用户关联到此群组。

Data Warehouse 会自动将任何大小超过 1 MB 的文件压缩为 zip 包。电子邮件附件的最大大小为 10 MB。

在针对各个计划报表和已下载报表的单个请求中，Data Warehouse 可处理无限数量的行。

>[!NOTE]
>
>“数据仓库”报告报告期间遇到的第一个值。

>[!IMPORTANT]
>
>分类分类值时，Analysis Workspace和数据仓库会以不同的方式对待“未指定”值。Workspace 中的“未指定”是指未分类的值，而 Data Warehouse 中的“未指定”是指您分类为“未指定”的值。

## Data Warehouse 请求描述 {#section_F21C78ED36884C389C852E876AF5CDE8}

此表描述“[!UICONTROL Data Warehouse 请求]”选项卡上的字段和选项。

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
    </ul> <p>有关虚拟报表包的 Data Warehouse 报表支持在虚拟报表包中配置的替代时区。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 可用区段</span> </td> 
   <td colname="col2"> <p>可让您选择要调查的访客群体，以及生成复杂区段。您可加载预配置区段、创建新区段，以及将区段组件存储于库中以用于生成其他区段。 </p> <p>现在您可以堆叠区段。在选择多个区段时，预览区域、请求管理器和“请求详细信息”弹出窗口会显示以逗号分隔的名称列表（例如，Segment1, Segment2）。 </p> <p>有关更多信息，请参阅[分段指南](/help/components/c-segmentation/seg-home. md)。 </p> <p>注意：您不能在同一个 Data Warehouse 报表的同一个区段中既包括区段过滤器，又包括划分。这样做会导致出错。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">划分</span> </td> 
   <td colname="col2"> <p>可让您使用划分对数据进行分类。区段与划分的不同之处在于：区段可从数据集中筛选数据，而划分能够将包含针对此划分的全部有效值的数据分为若干独立部分。 </p> 您还可以按一个或多个区段划分报表。但是，您不能在同一个 Data Warehouse 报表的同一个区段中既包括区段过滤器，又包括划分。这样做会导致出错。 <p> 例如，使用区段删除数据集中的性别，使用划分按性别查看分隔的数据。 </p> <p>在通过多个多值维度（例如，多个移动设备报表）提交 Data Warehouse 请求时，点击一次即可生成数量按照指数级别增长的行。可通过一次点击输出的行数的上限为 100（以前为 1000）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 量度</span> </td> 
   <td colname="col2">允许您添加要报告的指标。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 量度排序</span> </td> 
   <td colname="col2">提供排名的划分报表（按量度值从大到小排序），这与“Reports &amp; Analytics”用户界面、Data Workbench 等的显示情况类似。<a href="../../export/data-warehouse/sorting-by-metric.md#concept_7B7BDE3D42E549389DACA1E33B2FC1CC" format="dita" scope="local">更多信息...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 计划提交</span> </td> 
   <td colname="col2"> <p>可让您安排提交请求的时间，从而按选定的周期自动提交请求，或者作为一次性报表提交。如果采用默认格式，则此报表会在电子邮件中作为 .csv 文件送达。 </p> <p>若要添加日期范围，请在文件名中包含 <span class="filepath">%R</span>。这个值代表报表中请求的日期值。例如，如果您请求获得从 2013 年 5 月 1 日到 2013 年 5 月 7 日的数据，则 <span class="filepath">%R</span> 显示包含 20130501 - 20130507 日期范围的文件名。 </p> </td> 
  </tr> 
 </tbody> 
</table>

