---
description: Report Builder使用Analytics自定义日历。 您可以使用日历定义周和年的第一天，或者使用其他零售日历样式。 日历格式可用于多种用途，包括销售比较和预测标准化、工资单成本分析或实地盘点盘点法规。
title: 自定义日程表
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
TQID: https://experienceleague.adobe.com/At3YiOPV0jx5WXwe-VvA05n3yIEmiAJIRzoOoeISeA4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 19%

---

# 自定义日程表

{{legacy-arb}}

Report Builder使用Analytics自定义日历。 您可以使用日历定义周和年的第一天，或者使用其他零售日历样式。 日历格式可用于多种用途，包括销售比较和预测标准化、工资单成本分析或实地盘点盘点法规。

每种日历格式如下所述。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日程表 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>公历 </p> </td> 
   <td colname="col2"> <p> 使用传统的日历格式（1月至12月，每月包含30或31天以及可变的周数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已修改的公历 </p> </td> 
   <td colname="col2"> <p> 使用传统公历，但允许您选择一年的第一个月和一周的第一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4零售日历 </p> </td> 
   <td colname="col2"> <p> 按月中的周数划分。 也就是说一月有四个星期，以此类推。 全国零售联合会使用4-5-4日历格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义日历 </p> </td> 
   <td colname="col2"> <p> 提供了三种基于每月周数的格式。 每个月中的周数取决于所选的年度第一天。 </p> <p>一年有52个星期。 将其分为4个季度，则每季度可获得13周的时间。 但季度中只有3个月。 13 无法被 3 整除，因此最终要将多出的一周放入其中的一个月，以使其始终一致。 5/4/4表示季度的第一个月有额外的一周。 4/5/4表示第2个月有额外的一周，依此类推。在5-4-4日历中，将第53周添加到年的最后一个季度。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>：一月有四周，二月有五周，三月有四周，以此类推。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>：一月有四周，二月有四周，三月有五周，以此类推。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>：一月有五周，二月有五周，三月有四周，以此类推。 </li> 
    </ul> <p>注意：以下所有Adobe Analytics工具都支持此日历选项：Analysis Workspace、Report Builder和Activity Map。 但 Data Warehouse 例外，它不支持自定义日历。 </p> </td> 
  </tr> 
 </tbody> 
</table>
