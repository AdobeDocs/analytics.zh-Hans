---
description: 计算量度的方法有以下几种：标准、参与率、最近和线性。由于公式不同，每种方法在计算量度值时各有不同。
seo-description: 计算量度的方法有以下几种：标准、参与率、最近和线性。由于公式不同，每种方法在计算量度值时各有不同。
seo-title: 度量计算
solution: Analytics
title: 度量计算
topic: 量度
uuid: af58f1e-12c5-4828-ae39-c9 aaaef6 b705
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 度量计算

计算量度的方法有以下几种：标准、参与率、最近和线性。由于公式不同，每种方法在计算量度值时各有不同。

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度计算 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 原始 </td> 
   <td colname="col2"> <p>完整信用提供给与成功事件相关联的第一个变量值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最近 </td> 
   <td colname="col2"> <p>完整信用提供给与成功事件相关联的最后一个变量值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 线性 </td> 
   <td colname="col2"> <p>选择线性分配时，成功事件会被平均划分到访问期间见到的所有变量值。对于数值和货币事件，例如<span class="term"> 收入</span>，货币金额被划分。For counter events such as <span class="term"> Orders</span>, a fraction of the event is awarded to each variable value in the visit. 生成报表时会对这些部分进行合计，然后在报表中四舍五入为最接近的整数。 </p> <p>例如，在一次访问中，如果在成功事件之前访问了四个页面，则每个页面将收到该事件 25% 的信用。如果在同一次访问中，<span class="varname"> 营销活动</span> 具有两个值，每个营销活动值将获得该事件的50%信用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参与率 </td> 
   <td colname="col2"> <p>将完整信用分配给访问中对成功事件做出了贡献的每个变量值。如果您使用交叉访问参与率量度，则此计算还可以跨访客会话进行应用。 </p> <p>请参阅<a href="../../../components/c-variables/c-metrics/metrics-participation.md#concept_8E6B39106A244CB49E055150B291B477" format="dita" scope="local">参与率</a>以了解更多相关信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例 - 量度计算 {#section_4CE01DA35108418D9909823A7ECC4B45}

假设您的网站有一个内部搜索，并使用转化变量 (eVar) 对该搜索进行跟踪。访客在做出 $100 的购买决定前执行了多次内部搜索：

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt;$100购买

在报表中，信用分配如下所示：

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar 值 </th> 
   <th colname="col2" class="entry"> 首次 </th> 
   <th colname="col3" class="entry"> 最近 </th> 
   <th colname="col4" class="entry"> 线性 </th> 
   <th colname="col5" class="entry"> 参与率 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>宠物 </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>猫科动物 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>猫 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>小猫 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

