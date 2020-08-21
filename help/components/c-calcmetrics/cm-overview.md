---
description: 计算量度和高级计算（或派生）量度是指您可以从现有量度创建的自定义量度。
keywords: Calculated Metrics;Derived Metrics;Advanced Calculated Metrics
title: 计算量度和高级计算（派生）量度
uuid: 2553c115-b15a-4109-8de2-733dbc1eeb9e
translation-type: ht
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8
workflow-type: ht
source-wordcount: '783'
ht-degree: 100%

---


# 计算量度和高级计算（派生）量度

计算量度和高级计算（或派生）量度是指您可以从现有量度创建的自定义量度。

>[!IMPORTANT]
>
>2018 年 7 月，Adobe 引入了[归因 IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html)，这改进了计算量度中分配模型的计算方式。作为此更改的一部分，使用非默认分配模型的计算量度已迁移至改进的新归因模型。
>
>* “营销渠道最近联系”和“营销渠道首次联系”分配模型已分别迁移至新的“最近联系”和“首次联系”归因模型（注：“营销渠道”并没有被弃用 - 弃用的只有此处所述出现在计算量度中的这两个分配模型）。
>* 此外，我们还修正了线性分配的计算方式。对于通过“线性”分配模型使用计算量度的客户，报表可能会稍有变化，以反映修正后的新归因模型。计算量度的这一更改将反映在 [!UICONTROL Analysis Workspace]、[!UICONTROL Reports &amp; Analytics]、报表 API、Report Builder 和 Ad Hoc Analysis 中。有关详细信息，请参阅[线性分配将如何工作（自 2018 年 7 月 19 日起）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)。


我们的计算量度工具提供了一种高度灵活的方式，可用于生成、管理和组织量度。通过使用这些工具，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。每个 [!DNL Analytics] 包中可用的自定义量度包括：

* Adobe [!DNL Analytics] Foundation：计算量度
* [Adobe Analytics Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)：计算量度 + 高级计算量度
* [Adobe Analytics Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)：计算量度 + 高级计算量度
* [Adobe Analytics Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html)：计算量度 + 高级计算量度

以下是计算量度和高级计算量度功能的比较：

| Builder 选项 | 计算量度 | 高级计算（派生）量度 |
|---|---|---|
| [格式类型（小数、时间、百分比、货币）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [归因更改（默认、线性、参与率等）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [量度类型（标准、总数）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本运算符（加、减、乘、除） | 是 | 是 |
| [应用区段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 否 | 是 |
| [基本函数（计数、绝对值、平均值等）](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 否 | 是 |
| [高级函数（回归、if/then、t 分数等）](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 否 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 创建跨 [!UICONTROL Analysis Workspace]、[!UICONTROL Reports &amp; Analytics]、[!UICONTROL Ad Hoc Analysis]、[!UICONTROL Report Builder]、[!UICONTROL 异常检测]和[!UICONTROL 贡献分析]的量度。
* 创建在报表运行时派生的分段量度，而[不必更改实施](https://youtu.be/CuQTm9RaUpY)。这些量度可以在历史记录中查看，因为它们是基于区段的。
* 在报表包之间共享量度。这表示所有新创建的量度都适用于同一登录公司中的所有报表包。
* （仅限高级计算量度）量度上的区段。例如，您可以为“新访客”创建一个量度，其中包含首次进行会话的人员计数。
* （仅限高级计算量度）包含统计函数，以帮助您更好地描述数据。例如，您可以对报表中的项目数量进行计数，或为每个项目加入标准偏差数。
* 将在 [!UICONTROL Ad Hoc Analysis] 中创建的量度用于其他 [!DNL Analytics] 工具，反之亦然。

   >[!NOTE]
   >
   >您可以继续在 Ad Hoc Analysis 中创建量度。它的计算量度生成器用户界面现在类似于新量度生成器。

## 限制 {#section_CB878B02451541D68A68B508D4DBD19A}

某些 [!DNL Analytics] 功能让您可以使用事件，而不是计算量度：

* Reports &amp; Analytics 中的漏斗
* Analysis Workspace 中的流失
* [!UICONTROL Analysis Workspace 中的队列分析]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 区段]
* [!UICONTROL 实时报表]
* [!UICONTROL 当前数据报表]
* [!DNL Analytics] for [!DNL Target]

## 工具 {#section_D65E9C067E9C45E1A50DD30F50561BB2}

以下是[!UICONTROL 计算量度]工具的简短概述：

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工具 </th> 
   <th colname="col2" class="entry"> 功能 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md"  > 计算量度生成器</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">使用高级分配模型创建计算量度和高级计算量度。 </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">将内联区段添加到量度公式中。 </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">比较同一报表中的区段。例如，比较本地访客与国际访客。 </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">使用统计函数。 </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">提供详细的量度描述（显示其用途，以及何处可以使用，何处不可以使用）。 </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">将定义复制到新量度中。 </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">提供内联量度预览。 </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">设置量度极性，以指示当给定的自定义事件（量度）上升时是有利还是不利。 </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">标记量度。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md"  > 计算量度管理器</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">与他人共享量度。 </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">批准和管理量度。 </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">组织（标记）量度，以方便用户查找。 </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">删除量度。 </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">重命名量度。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度选择器边栏 </td> 
   <td colname="col2"> <p>替换 <span class="uicontrol">Reports &amp; Analytics</span> 中的“<span class="uicontrol">显示量度</span>”弹出菜单。 </p> <p>它允许您搜索量度，并将量度添加到/应用于报表。您还可以更改<a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md"  >排序</a>（选项包括：“按字母顺序”、“推荐”、“经常使用”、“最近使用”。）此外，您还可以对报表包进行过滤，以便仅显示在特定报表包中创建的量度。 </p> <p>要访问此“量度选择器”，请单击报表左侧的“量度”图标 <img placement="inline"  src="assets/metrics_icon.png" width="30px" id="image_2C6F20B4E634486B95BACD4CA47EF991" />。量度选择器具有如下外观： </p> <p><img src="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/README.md"  > 适用于计算量度的 API</a> </td> 
   <td colname="col2"> <p>Adobe Analytics 2.0 API 集的组成部分。 </p> </td> 
  </tr> 
 </tbody> 
</table>

