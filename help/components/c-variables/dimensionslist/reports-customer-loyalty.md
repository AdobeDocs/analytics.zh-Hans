---
description: 客户忠诚度显示客户的购买类型。
seo-description: 客户忠诚度显示客户的购买类型。
seo-title: 客户忠诚度
solution: Analytics
title: 客户忠诚度
topic: 报表
uuid: 7dc30b57-7b18-4228-a6 ab-6b66 b3 d9402
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 客户忠诚度

客户忠诚度显示客户的购买类型。

该报表根据四种忠诚度类别显示客户的购买类型：

* 非客户
* 新客户
* 回头客户
* 忠诚客户

虽然可以在此报表中查看非购买量度（例如，自定义事件、购物车事件等），这三个类别始终以订单数为依据。例如，某访客可能会在报表中添加一个名为“内部搜索”的自定义事件。[!UICONTROL 回头客户]行项目显示的是之前已经购物达两次的访客执行的内部搜索次数，而不是已执行两次内部搜索的访客数。

**客户忠诚度处理**

下表定义了 Analysis Workspace、“Reports &amp; Analytics”、Ad Hoc Analysis 和 Data Warehouse 当前处理客户忠诚度的方式：

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>2016 年 5 月 19 日之后 </p> </th> 
   <th colname="col3" class="entry"> <p>2016 年 4 月 21 日至 5 月 19 日 </p> <p>（不适用于 Data Warehouse） </p> </th> 
   <th colname="col4" class="entry"> <p>2016 年 4 月 21 日之前 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>非客户 </p> </td> 
   <td colname="col2"> <p>从未购买过产品的访客 </p> </td> 
   <td colname="col3"> <p>访问结束前未购买过产品的访客。 </p> </td> 
   <td colname="col4"> <p>不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新客户 </p> </td> 
   <td colname="col2"> <p>购买过 1 次产品的访客 </p> </td> 
   <td colname="col3"> <p>该次访问结束前购买过 1 次产品的访客。 </p> <p>（如果购买了产品，则客户状态会在该次购买后的下次访问时进行更新。） </p> </td> 
   <td colname="col4"> <p>该次访问结束前未购买过产品的访客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>回头客户 </p> </td> 
   <td colname="col2"> <p>购买过 2 次产品的访客 </p> </td> 
   <td colname="col3"> <p>在第 2 次购买产品的访问结束前购买过 2 次产品的访客。 </p> <p>（如果购买了产品，则客户状态会在该次购买后的下次访问时进行更新。） </p> </td> 
   <td colname="col4"> <p>在当次购买产品的访问结束前购买过 1 次产品的访客。 </p> <p>（如果购买了产品，则客户状态会在该次购买后的下次访问时进行更新。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>忠诚客户 </p> </td> 
   <td colname="col2"> <p>购买过 3 次以上（含 3 次）产品的访客 </p> </td> 
   <td colname="col3"> <p>在最近购买产品的访问结束前购买过 3 次以上（含 3 次）产品的访客。 </p> <p>（如果购买了产品，则客户状态会在该次购买后的下次访问时进行更新。） </p> </td> 
   <td colname="col4"> <p>在最近购买产品的访问结束前购买过 2 次以上（含 2 次）产品的访客。 </p> <p>（如果购买了产品，则客户状态会在该次购买后的下次访问时进行更新。） </p> </td> 
  </tr> 
 </tbody> 
</table>

| 版本 14 客户忠诚度（当前） |
|---|
| 新客户 | 1 次访问和 1 次购物 |
| 回头客户 | 1 次以上的访问和 2 次购物 |
| 忠诚客户 | 1 次以上的访问和 3 次以上的购物 |

忠诚度状态会在同一次访问期间内根据购买事件立即更改。例如，新客户（购物 1 次）购物一次，并在此次购物后的同一访问期间订阅了新闻。则此次新闻订阅事件将被视为回头客户互动，因为该访客的客户忠诚度状态在购买事件发生后已立即更改。
