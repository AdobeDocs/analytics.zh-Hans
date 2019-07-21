---
description: 选择量度旁边的齿轮图标允许您指定量度类型和归因模型。
seo-description: 选择量度旁边的齿轮图标允许您指定量度类型和归因模型。
seo-title: 量度类型和归因
title: 量度类型和归因
uuid: 64649698-df2 a-42c3-bb31-938f766 e1 d1 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 量度类型和归因

选择量度旁边的齿轮图标允许您指定量度类型和归因模型。

* [量度类型](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [列归因模型](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [线性分配工作原理（自 2018 年 7 月 19 日起）](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## 量度类型 {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| 量度类型 | 定义 |
|---|---|
| 标准 | These metrics are the same metrics used in standard [!DNL Analytics] reporting. 如果公式包含一个标准量度，它会显示与其相对的非计算量度的相同数据。标准量度可用于创建特定于每个单独行项目的计算量度。For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item. |
| 合计 | 使用每个行项目中报告时段的合计。如果公式包含一个合计量度，它会显示每个行项目中的相同合计数。合计量度可用于创建与网站合计数据相比较的计算量度。For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item. |

## 列归因模型 {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>In July 2018, [!DNL Analytics] introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. 作为此更改的一部分，使用非默认分配模型的计算量度已迁移至改进的新归因模型。
>
>* 有关支持的非默认归因模型和回顾窗口的完整列表，请参阅[归因 IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) 文档。
>* “营销渠道最近联系”和“营销渠道首次联系”分配模型将分别迁移至新的“最近联系”和“首次联系”归因模型（注：“营销渠道”并不会被弃用——弃用的只有此处所述出现在计算量度中的这两个分配模型）。
>* 此外，我们还将修正线性分配的计算方式。对于通过“线性”分配模型使用计算量度的客户，报表可能会稍有变化，以反映修正后的新归因模型。This change to calculated metrics will be reflected in Analysis Workspace, [!UICONTROL Reports &amp; Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. 有关更多信息，请参阅[线性分配工作原理（自 2018 年 7 月 19 日起）](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)。
>



## 线性分配工作原理（自 2018 年 7 月 19 日起） {#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

Adobe于2018年月更改了计算量度线性分配的方式。This change impacts Analysis Workspace, Ad Hoc Analysis, [!UICONTROL Reports &amp; Analytics], Report Builder, Activity Map, and the Reporting APIs. 此更改将主要影响具有持久性的 eVar 与其他维度。Note that these changes will only apply to calculated metrics and will not impact other reports using linear allocation (such as the Pages report in [!UICONTROL Reports &amp; Analytics]). 其他使用线性分配的报表将继续使用现有的线性分配方式。

下例说明了使用线性分配的计算量度将在报告时发生何种变化：

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> 第 1 次点击 </th> 
   <th colname="col3" class="entry"> 第 2 次点击 </th> 
   <th colname="col4" class="entry"> 第 3 次点击 </th> 
   <th colname="col5" class="entry"> 第 4 次点击 </th> 
   <th colname="col6" class="entry"> 第 5 次点击 </th> 
   <th colname="col7" class="entry"> 第 6 次点击 </th> 
   <th colname="col8" class="entry"> 第 7 次点击 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>发送的数据 </p> </td> 
   <td colname="col2"> 促销活动 A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促销活动 A </td> 
   <td colname="col5"> 促销活动 B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促销活动 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最近联系 eVar </p> </td> 
   <td colname="col2"> 促销活动 A </td> 
   <td colname="col3"> 促销活动 A </td> 
   <td colname="col4"> 促销活动 A </td> 
   <td colname="col5"> 促销活动 B </td> 
   <td colname="col6"> 促销活动 B </td> 
   <td colname="col7"> 促销活动 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次联系 eVar </p> </td> 
   <td colname="col2"> 促销活动 A </td> 
   <td colname="col3"> 促销活动 A </td> 
   <td colname="col4"> 促销活动 A </td> 
   <td colname="col5"> 促销活动 A </td> 
   <td colname="col6"> 促销活动 A </td> 
   <td colname="col7"> 促销活动 A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>示例 Prop </p> </td> 
   <td colname="col2"> 促销活动 A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促销活动 A </td> 
   <td colname="col5"> 促销活动 B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促销活动 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

此示例中，在第 7 次点击进行了价值 10 美元的购买之前，值 A、B、C 已发送到第 1、3、4、6 次点击上的变量之中。第二行显示出，在这一系列的点击中，这些值均一直持久出现在最近联系访问中。第三行则显示出首次联系访问的持久性。最后，最后一行显示的是某个不具有持久性的属性 (Prop) 其数据是如何记录的。

**线性分配工作原理概要（2018 年 7 月之前）**

在 2018 年 7 月 19 日之前，线性分配是在首次联系持久性或最近联系持久性出现之后进行计算。即，对于上述示例中的最近联系 eVar，10 美元将以如下方式分配：A = 10 * (3/6) = $5，B = 10 * (2/6) = $3.33，C = 10 * (1/6) = $1.67。

而对于上述首次联系 eVar，所有 10 美元都将分配给 A。对于该 Prop，则按如下方式分配：A = 10 * (2/4) = $5，B = 10 * (1/4) = $2.50，C = 10 * (1/4) = $2.50。以前，线性分配的工作原理总结如下：

| 值 | 最近联系 eVar 当前分配值 | 首次联系 eVar 当前分配值 | Prop 当前分配值 |
|---|---|---|---|
| 促销活动 A | $5.00 | $10.00 | $5.00 |
| 促销活动 B | $3.33 | $0 | $2.50 |
| 促销活动 C | $1.67 | $0 | $2.50 |
| 合计 | $10.00 | $10.00 | $10.00 |

**线性分配工作原理概要（自 2018 年 7 月 19 日起）**

从 2018 年 7 月 19 日起，我们修改了计算量度中的此种方式。[!DNL Analytics] 现在，只使用传入的值(顶部表的第一行)，而不是基于上次触摸或首次触摸使用持久值。基于此，维度分配设置不会再影响线性分配的计算方式（这意味着 Prop 和 eVar 都将以相同方式得到处理）；结果将反映最初传递的内容，而不是反映那些可能具有持久性的首次或最近联系值。因此，在上述所有三种情况下，均为：A = 10 * (2/4) = $5，B = 10 * (1/4) = $2.50，C = 10 * (1/4) = $2.50。

| 值 | 最近联系 eVar 新分配值 | 首次联系 eVar 新分配值 | Prop 新分配值 |
|---|---|---|---|
| 促销活动 A | $5.00 | $5.00 | $5.00 |
| 促销活动 B | $2.50 | $2.50 | $2.50 |
| 促销活动 C | $2.50 | $2.50 | $2.50 |
| 合计 | $10.00 | $10.00 | $10.00 |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

