---
title: 哈希冲突
description: 描述什么是哈希冲突以及它是如何体现的。
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 100%

---

# 哈希冲突

Adobe 会将 prop 和 eVar 值视为字符串，即使这个值是一个数字。这些字符串有时长达数百个字符，有时却很短。为了节省空间、提升性能，并确保所有的值都能够大小一致，在处理时将不会直接使用这些字符串。而是为每个值计算一个 32 位或 64 位的哈希值。所有报表都基于这些哈希值运行，其中每个哈希值都会被替换为原始文本。哈希可大幅提高 Analytics 报表的性能。

对于大多数字段而言，字符串首先会转换为全部小写（减少唯一值的数量）。这些值每月进行一次哈希运算（每月首次出现的时候进行运算）。月复一月，可能会出现两个唯一的变量值经过哈希运算后变成同一个值的情况，但这种可能性很小。这一概念就是所谓的&#x200B;*哈希冲突*。

在报表中，哈希冲突可能会以下列形式体现：

* 如果您观察某个值的趋势，发现在一个月内出现猛增，则可能是这个变量的另外一些值通过哈希运算变成了与您正在观察的值相同的值。
* 特定值的区段会发生同样的事情。

## 哈希冲突示例

哈希冲突出现的可能性会随着维度中唯一值的数量而增加。例如，当月晚些时候获取的某一个值可能会与当月早些时候获取的某一个值拥有相同的哈希值。以下示例可以帮助解释，这种情况如何能够导致区段结果发生变化。假设 eVar62 于 2 月 18 日收到“value 100”。Analytics 会保留一个类似于这样的表格：

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
