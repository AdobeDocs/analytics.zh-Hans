---
description: Report Builder 使用 Analytics 的自定义日历。您可以使用该日历定义周和年的第一天，或者使用其他零售日历样式。日历格式可用于多种用途，包括销售额比较和预测标准化、工资单费用分析或实际库存计数调节。
title: 自定义日历
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 95%

---

# 自定义日历

{{legacy-arb}}

Report Builder 使用 Analytics 的自定义日历。您可以使用该日历定义周和年的第一天，或者使用其他零售日历样式。日历格式可用于多种用途，包括销售额比较和预测标准化、工资单费用分析或实际库存计数调节。

每种日历格式介绍如下。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日历 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>公历 </p> </td> 
   <td colname="col2"> <p> 使用传统的日历格式（1 月到 12 月，每月包括 30 或 31 天，并且每月具有不同的周数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已修改的公历 </p> </td> 
   <td colname="col2"> <p> 使用传统的公历，但您可以选择年度的第一个月份和周的第一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 零售日历 </p> </td> 
   <td colname="col2"> <p> 按一个月中的周数划分每个月。即 1 月份有 4 周，依此类推。全国零售联盟使用 4-5-4 日历格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义日历 </p> </td> 
   <td colname="col2"> <p> 提供三个基于每月周数的格式。每个月中的周数取决于所选的年度第一天。 </p> <p>一年有 52 周。将它们分为四个季度，则每个季度有 13 周。但是一个季度有三个月。13 无法被 3 整除，因此最终要将多出的一周放入其中的一个月，以使其始终一致。5/4/4 表示季度的第 1 个月拥有多出的一周。4/5/4 表示季度的第 2 个月拥有多出的一周，以此类推。在 5-4-4 日历中，将在一年的最后一个季度中添加第 53 周。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>：一月有四周，二月有五周，三月有四周，以此类推。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>：一月份拥有四周，二月份拥有四周，三月份拥有五周，以此类推。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>：一月份拥有五周，二月份拥有五周，三月份拥有四周，以此类推。 </li> 
    </ul> <p>注意：以下所有Adobe Analytics工具都支持此日历选项：Analysis Workspace、Report Builder和Activity Map。 但 Data Warehouse 例外，它不支持自定义日历。 </p> </td> 
  </tr> 
 </tbody> 
</table>
