---
title: 哈希冲突
description: 描述什么是哈希冲突以及它是如何体现的。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 哈希冲突

Adobe将prop和eVar值视为字符串，即使该值是数字也是如此。 这些字符串有时长达数百个字符，有时却很短。为了节省空间、提高性能并使所有内容均匀地调整大小，字符串不直接用于处理。 而是为每个值计算一个 32 位或 64 位的哈希值。所有报告都运行于这些哈希值上，其中每个哈希值都由原始文本替换。 散列可大幅提高Analytics报告的性能。

对于大多数字段而言，字符串首先会转换为全部小写（减少唯一值的数量）。这些值每月进行一次哈希运算（每月首次出现的时候进行运算）。从月份到月份，两个唯一变量值散列到相同值的可能性很小。 This concept is known as a *hash collision*.

在报表中，哈希冲突可能会以下列形式体现：

* 如果您观察某个值的趋势，发现在一个月内出现猛增，则可能是这个变量的另外一些值通过哈希运算变成了与您正在观察的值相同的值。
* 特定值的区段会发生同样的事情。

## 哈希冲突示例

哈希冲突出现的可能性会随着维度中唯一值的数量而增加. 例如，当月晚些时候获取的某一个值可能会与当月早些时候获取的某一个值拥有相同的哈希值。以下示例可以帮助解释这如何导致区段结果发生更改。 假设 eVar62 于 2 月 18 日收到“value 100”。Analytics 会保留一个类似于这样的表格：

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 字符串值 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Value 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Value 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

如果您构建一个区段，用来寻找 eVar62=&quot;value 500&quot; 的访问，那么 Analytics 会确定 &quot;value 500&quot; 是否包含一个哈希。因为如果 &quot;value 500&quot; 不存在，那么 Analytics 会返回零个访问。然后到 2 月 23 日，eVar62 收到了 &quot;value 500&quot;，而且这个值的哈希也是 123。表格如下：

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 字符串值 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Value 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Value 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Value 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

再次运行同一个区段时，这个区段在寻找 &quot;value 500&quot; 的哈希时找到了 123，然后报表会返回所有包含哈希 123 的访问。现在，发生在 2 月 18 日的访问就会被包含在结果中。

使用 Analytics 时，这种情况会产生问题。Adobe 仍在研究方法，希望将来能够降低出现此类哈希冲突的可能性。要想避免这种情况，我们的建议是想办法分散各个变量的唯一值、利用处理规则删除不必要的值，或者通过其他方式减少各个变量的值的数量。
