---
description: 通过选择度量旁边的齿轮图标，可以指定度量类型和归因模型。
title: 量度类型和归因
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# 量度类型和归因

通过选择度量旁边的齿轮图标，可以指定度量类型和归因模型。

* [量度类型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [列归因模型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [线性分配的工作原理（自2018年7月19日起）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## 量度类型 {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| 量度类型 | 定义 |
|---|---|
| 标准 | 这些量度是在标准 [!DNL Analytics] 报表中使用的相同量度。如果公式由单个标准度量组成，则它显示与其非计算度量对应的相同数据。 标准量度可用于创建特定于每个单独行项目的计算量度。 例如，[订购次数]/[访问次数]是将特定行项目的订购次数除以特定行项目的访问次数。 |
| 合计 | 在每个行项目中使用报告期间的合计。 如果公式由单个总量度组成，则在每个行项目上显示相同的总数。 总量度可用于创建与站点总数据进行比较的计算量度。 例如，[订购次数]/[总访问次数]会显示订购次数与网站所有访问次数的比例，而不只是与特定行项目访问次数的比例。 |

## 列归因模型 {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>2018 年 7 月，[!DNL Analytics] 引入了[归因 IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html)，这改进了计算量度中分配模型的计算方式。作为此更改的一部分，使用非默认分配模型的计算量度已迁移至改进的新归因模型。
>
>* 有关非默认归因模型和支持回顾窗口的完整列表，请参阅 [Attribution IQ文档](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) 。
>* “营销渠道最近联系”和“营销渠道首次联系”分配模型将分别迁移至新的“最近联系”和“首次联系”归因模型（注：“营销渠道”并不会被弃用 - 弃用的只有此处所述出现在计算量度中的这两个分配模型）。
>* 此外，我们还将修正线性分配的计算方式。对于通过“线性”分配模型使用计算量度的客户，报表可能会稍有变化，以反映修正后的新归因模型。计算量度的这一更改将反映在 Analysis Workspace、Reports &amp; Analytics、报表 API、Report Builder 和 Ad Hoc Analysis 中。有关详细信息，请参 **阅线性分配的工作原理(自2018年7月19日起**,)。
>



## 线性分配的工作原理（自2018年7月19日起）

2018 年 7 月，Adobe 更改了计算量度中线性分配的报告方式。这一更改将会影响 Analysis Workspace、Ad Hoc Analysis、Reports &amp; Analytics、Report Builder、Activity Map 和报表 API。此更改将主要影响具有持久性的 eVar 与其他维度。请注意，这些更改只会应用于计算量度，而不会对其他使用线性分配的报表产生影响（例如 Reports &amp; Analytics 中的“页面”报表）。其他使用线性分配的报表将继续使用现有的线性分配方法。

以下示例说明具有线性分配的计算度量在报告中将如何变化：

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> 点击1 </th> 
   <th colname="col3" class="entry"> 点击2 </th> 
   <th colname="col4" class="entry"> 点击3 </th> 
   <th colname="col5" class="entry"> 点击4 </th> 
   <th colname="col6" class="entry"> Hit 5 </th> 
   <th colname="col7" class="entry"> Hit 6 </th> 
   <th colname="col8" class="entry"> Hit 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>发送数据 </p> </td> 
   <td colname="col2"> 促销A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促销A </td> 
   <td colname="col5"> 促销B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> Promo C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次联系eVar </p> </td> 
   <td colname="col2"> 促销A </td> 
   <td colname="col3"> 促销A </td> 
   <td colname="col4"> 促销A </td> 
   <td colname="col5"> 促销B </td> 
   <td colname="col6"> 促销B </td> 
   <td colname="col7"> Promo C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次接触eVar </p> </td> 
   <td colname="col2"> 促销A </td> 
   <td colname="col3"> 促销A </td> 
   <td colname="col4"> 促销A </td> 
   <td colname="col5"> 促销A </td> 
   <td colname="col6"> 促销A </td> 
   <td colname="col7"> 促销A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>示例prop </p> </td> 
   <td colname="col2"> 促销A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促销A </td> 
   <td colname="col5"> 促销B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> Promo C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

在此示例中，值A、B和C在点击1、3、4和6之前被发送到一个变量中，然后在点击7时进行$10的购买。 在第二行中，这些值会在最后一次点击访问的基础上跨点击保留。 第三行说明了首次接触访问的持久性。 最后，最后一行说明了如何为没有持久性的prop记录数据。

## 线性分配在2018年7月之前是如何运作的

在2018年7月19日之前，线性归因是在首次接触或最近接触持久性已发生之后计算的。 这意味着对于上述最后一次eVar,10美元将按如下方式分发：A = 10 *(3/6)= $5,B = 10 *(2/6)= $3.33,C = 10 *(1/6)= $1.67。

对于上述首次接触eVar，所有10美元都将捐给A。对于prop:A = 10 *(2/4)= $5,B = 10 *(1/4)= $2.50,C = 10 *(1/4)= $2.50。要按以前的工作方式汇总线性分配，请执行以下操作：

| 值 | 当前最近联系eVar | 当前首次触摸eVar | 当前Prop |
|---|---|---|---|
| 促销A | $5.00 | $10.00 | $5.00 |
| 促销B | $3.33 | $0 | $2.50 |
| Promo C | $1.67 | $0 | $2.50 |
| 合计 | $10.00 | $10.00 | $10.00 |

**截至2018年7月19日线性分配的工作方式摘要**

在7月19日之后，我们纠正了计算量度中的这一行为。 现在，[!DNL Analytics] 不再基于最近联系或首次联系使用持久值，而是仅使用传入的值（即顶部表中的第一行）。因此，维分配设置不再影响线性分配的计算方式（这意味着prop和eVar将以相同的方式处理），并且结果反映最初传入的内容而不是可能持续存在的第一个或最后一个接触值。 因此，在所有三种情况下，A = 10 *(2/4)= $5,B = 10 *(1/4)= $2.50,C = 10 *(1/4)= $2.50。

| 值 | 新的最近联系eVar | 新的首次触摸eVar | 新属性 |
|---|---|---|---|
| 促销A | $5.00 | $5.00 | $5.00 |
| 促销B | $2.50 | $2.50 | $2.50 |
| Promo C | $2.50 | $2.50 | $2.50 |
| 合计 | $10.00 | $10.00 | $10.00 |

