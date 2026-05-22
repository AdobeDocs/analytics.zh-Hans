---
description: 了解异常检测及其计算方式。
title: 如何使用异常检测自动查找趋势
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 18%

---

# 异常检测{#anomaly-detection}

{{legacy-arb}}

异常检测使用统计建模，自动查找数据中的意外趋势。 该模型可分析量度并确定值的下限、上限和预期范围。 如果发生意外的尖峰或低谷，系统会在报表中进行警报。

您可能会调查的异常情况包括：

* 平均订单价值显著降低
* 低收入订单的剧增
* 试用版注册量剧增或骤降
* 登陆页面浏览量骤降
* 视频缓冲事件中的香料
* 视频低码率剧增

>[!NOTE]
>
>仅当您选择“日”粒度时，才可使用“异常检测”。

<p class="head"> <b>异常检测量度</b> </p>

异常检测会为您选择的每个量度添加新的量度值，包括：

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 下限 </td> 
   <td colname="col2"> <p>预测间隔的较低级别。 低于此级别的值被视为异常。 </p> <p>表示值将高于此级别的95%置信度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 预期 </td> 
   <td colname="col2"> <p>基于数据分析的预测值。 此值也是上界和下界之间的中点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上限 </td> 
   <td colname="col2"> <p>预测间隔的上限。 超过此级别的值被视为异常。 </p> <p>表示数值将低于此级别的95%置信度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder将这些值应用于所选量度。 例如，如果您选择页面查看次数量度并应用异常检测，则使用&#x200B;*`Page Views Lower Bound`*&#x200B;量度。

**异常检测的计算方式**

异常检测使用训练时段来计算、学习和报告每天的预测间隔数据。 培训期是历史时段，用于识别正常与异常的内容，并将所学内容应用于报告期。 在市场营销报表中，提供了培训期30、60和90。 在Report Builder中，30天可用。

培训期不一定与选定报告期相同。 报表图形显示您在日历中指定的日期范围期间。

为了计算数据，使用以下每个算法将每个量度的每日总数与培训时段进行比较：

* Holt Winters乘法（三指数平滑）
* Holt Winters加性（三指数平滑）
* 霍尔特趋势校正（双指数平滑）

每个算法都用来确定误差平方和(SSE)最小的算法。 然后，计算平均绝对百分比误差(MAPE)和当前标准误差，以确保模型在统计上有效。

可以扩展这些算法，以便为未来时段提供量度的预测预测。

由于培训期因报告期的开始而异，您可能会看到作为两个不同时间段的一部分为同一日期报告的数据存在差异。

例如，如果您在1月1日至14日运行报表，然后在1月7日至21日运行报表，则可能会在1月7日至14日期间，在两个不同的报表中看到同一量度的不同预测数据。 这是训练周期不同造成的。

| 报告范围 | 培训期 |
|--- |--- |
| 1月1日–14日 | 11月27日 — 12月31日 |
| 1月7日–21日 | 12月4日 — 1月6日 |
