---
description: 您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。
title: 异常检测概述
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 70%

---

# 异常检测概述

您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。贡献分析可与异常检测结合使用，以帮助识别导致异常的原因。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [异常检测](https://video.tv.adobe.com/v/40730?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Adobe Analytics Select和Adobe Analytics Foundation客户只能访问Workspace中的&#x200B;*每日粒度*&#x200B;异常检测。 有关更多信息，请参阅[异常检测和贡献分析授权](#anomaly-detection-and-contribution-analysis-entitlements)。

## 异常检测

“异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。

通过异常检测，您可以将“真实形势”与“假象”区分开来，然后确定对这些形势或异常造成影响的潜在因素。换言之，该功能可让您确认哪些统计波动会造成影响，而哪些不会。然后您便可以确认真正异常的根本原因。此外，您可以获得可靠的量度 (KPI) 预测。

您可能会调查的异常情况包括：

* 平均订单值的显著降低
* 低收入订单的剧增
* 试用注册量剧增或骤降
* 登录页面查看次数骤降
* 视频缓冲事件剧增
* 低视频比特率剧增

异常检测和[贡献分析](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/anomaly-detection/anomaly-detection)是 Analysis Workspace 中的核心工作流程。您可以针对任何每日异常运行“贡献分析”，并将结果嵌入到您的 Analysis Workspace 项目中。

Analysis Workspace 的异常检测算法包括

* 对每小时、每周和每月粒度以及现有的每天粒度的支持。
* 季节性（如“黑色星期五”）和假日的概念。

## 贡献分析

贡献分析可发现数据中的隐藏模式以解释统计异常并确定其背后的关联

* 意外的客户操作，
* 界外值，和
* 突然尖峰或下降

对于收敛受众区段中的选定量度。


>[!BEGINSHADEBOX]

有关演示视频，请参阅![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [贡献分析](https://video.tv.adobe.com/v/40762?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


发生了异常情况。为什么？您的异常检测报表显示订购次数存在不寻常的上升，您想知道为什么出现这种情况。发生了什么不寻常的情况？谁响应了哪个促销活动或转接链接？这一情况是否会传播开来？导致本异常的具体因素是什么？或许最重要的是，如何捕获有关客户的重要信息以及如何重现这一情况？（或者，如果量度下降或负量度上升，将来如何避免这种情况发生？）

贡献分析可帮助您立即评估数据，回答异常发生的原因。它可以在几秒钟内完成对异常的贡献划分（以前完成此过程需要用几周时间），从而提供受众区段的图表，并帮助描述客户交互情况。您可以战略性地使用贡献分析，以识别和捕获有意义的关联。 然后，从战略上利用这些关联来开发新的受众区段，或者在战术上识别触发警报的绑定外活动或欺诈活动。

[异常检测](#anomaly-detection)根据选定的量度和选定的受众区段来确定数据峰值和统计上的急速下跌。异常检测根据训练时段设置历史基准，然后绘制与特定事件关联的极度偏移。 异常检测可以报告正“订购”量度中的急速上升，或负“跳出次数”量度中的上升，也可以报告这两个量度中的下降情况，从而捕获在统计上相关的数据点，以供“贡献分析”进行评估。 确定了统计异常之后，您可以通过“贡献分析”进行深化，跨所有异常数据点评估相关的营销和促销活动变量。它将运行高级算法和机器学习流程来评估导致明显上升或下降的关联。然后在交互式可视化中显示这些计算结果，此类可视化旨在让您了解事情的各个方面以帮助回答发生各种情况的原因以及如何应对。

贡献分析可帮助您开发叙述来描述异常发生的原因。 以及如何应对异常、捕获相关量度并确定隐藏点，从而为您提供受众交互和客户兴趣趋势的总体原因。 有时，异常很容易发现和更正，如错误订购 2,000 艘橡皮船。而有时，异常会非常复杂，如确定某个地区在一个时间段仅针对特定目标促销活动突然出现的趋势。通过将各个维度中量度的贡献项目及其关联综合到一起，可让您全面了解您的受众交互，并且可帮助提供异常数据点的环境。

下面是一些用例：

* 通过监控产品需求的变化确定再营销的潜力。
* 通过响应特定的受众兴趣提升客户体验。
* 及早将欺骗性订单标识为越界报表。
* 通过识别高使用率和下载率保护自己免受商业间谍侵害。
* 监控操作，例如报告缺少JavaScript标记。

在全面分析了异常之后，将为排名最前的项目生成贡献摘要，并按总出现次数和项目的贡献值百分比进行排序。通过标准化的贡献得分，您可以轻松与其他重要维度项目进行比较、对照和关联。

## 贡献分析令牌

在 Analysis Workspace 中，所有具有“贡献分析”授权的客户每月均可运行有限次数的完整贡献分析。贡献分析&#x200B;**不包括**&#x200B;个点产品(SiteCatalyst 15)客户、Analytics Foundation客户和Analytics Select客户，这些客户无权使用贡献分析。

每个公司的运行次数受月度令牌的限制，而这些令牌是根据公司购买的 Adobe Analytics 产品授予的。每个公司的运行次数包括限制贡献分析访问权限以避免令牌滥用的功能。

## 常见问题解答 {#section_11D0431AD2014B96AB9561CA66A367CE}

| 问题 | 回答 |
| --- | --- |
| Adobe 为何要引入令牌？ | “贡献分析”一直是 Adobe Analytics 中最为强大的一项功能。通过允许您每月运行少量完整贡献分析（对于某些Analytics产品不仅仅是运行3个维度），您可以了解不受限的完整贡献分析可以为您做什么。 |
| 贡献分析中的令牌如何工作？ 是在加载具有现有贡献分析的项目时需要令牌，还是只有在运行全新的贡献分析时才需要令牌？ | 每个登录公司（而非每个用户）每月可获得一定数量的令牌，以便能够在 Analysis Workspace 中运行“完整”贡献分析。每次生成新的贡献分析时，都需要支付一个令牌。加载具有预运行贡献分析的项目时不需要支付令牌。 |
| 如果我的公司用完了令牌，但是想要运行其他的贡献分析，该怎么做？ | 您可以升级到其他 Adobe Analytics 产品，例如从 Standard（每月 2 个令牌）升级到 Ultimate（每月 20 个令牌）。您无法购买更多令牌。 您必须在现有的打包框架内升级。 |
| 我如何限制对贡献分析的访问？ | 默认情况下，只有管理员可以运行贡献分析。但是，管理员可以通过在 [Adobe Admin Console](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-console/home) 中创建权限组，向其他用户授予访问权限。仅向具有正当理由使用贡献分析，且确信不会滥用其访问权限的用户授予使用贡献分析的权限。 该权限称为[!UICONTROL 贡献分析]，位于[!UICONTROL 报表包工具]下。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-console/permissions/report-suite-tools) |
| 如何知道我的公司每月有权使用多少个令牌，以及我的公司在本月使用了多少个令牌？ | 转到[!UICONTROL 管理员] > [!UICONTROL 所有管理员] >[!UICONTROL “公司设置”主页] >[!UICONTROL 查看功能访问级别]。查看<ul><li>贡献分析：每月的使用令牌数量</li><li>贡献分析：本月所用的使用令牌数量</li></ul> |

## 异常检测和贡献分析授权 {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

以下是 Analysis Workspace 中异常检测和贡献分析的详细授权列表。

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adobe Analytics 授权 </th> 
   <th colname="col2" class="entry"> 异常检测 </th> 
   <th colname="col3" class="entry"> 贡献分析 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>基础 </p> </td> 
   <td colname="col2"> <p>仅每天粒度 </p> </td> 
   <td colname="col3" colsep="1"> <p>无令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>仅每天粒度 </p> </td> 
   <td colname="col3"> <p>无令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&amp;mv=other"  > Prime </a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 10 个令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 20 个令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>无限制令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标准 </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics 核心 </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 个令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（360，属性） </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>每月 2 个令牌 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium（完整，<a href="https://business.adobe.com/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>） </p> </td> 
   <td colname="col2"> <p>是 </p> </td> 
   <td colname="col3"> <p>无限制令牌 </p> </td> 
  </tr> 
 </tbody> 
</table>
