---
description: 在 Workspace 项目中运行贡献分析报表。
title: 运行贡献分析
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 15%

---

# 运行贡献分析

[贡献分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)是一个密集型机器学习过程，旨在揭示导致在 Adobe Analytics 中观察到异常的各项因素。意图在于协助用户以远快于其他方式的速度找到焦点领域或时机以供进行其他分析。

>[!NOTE]
>
>仅对具有每日粒度的数据支持贡献分析。

运行贡献分析的步骤包括：

1. 在项目中调用贡献分析。

   ![运行贡献分析](assets/run-contribution-analysis.png)

   1. 在折线图可视化图表中，基于具有每日粒度的自由格式表，选择一个异常数据点。 从弹出窗口中，选择&#x200B;**[!UICONTROL 分析]**。
   1. 在使用每天粒度的自由格式表中，从任意行的上下文菜单中选择&#x200B;**[!UICONTROL 运行贡献分析]**。 您甚至可以对未显示任何异常的行运行分析。
   1. 在使用每天粒度的自由格式表中，位于指示异常的行上：
      1. 选择指示器◥。
      1. 从![警报](/help/assets/icons/Alert.svg) **[!UICONTROL 检测到的异常]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 打开贡献分析]**。



1. （可选）您可以通过[排除维度](#exclude-dimensions)来缩小分析范围（并且因此而提高分析速度）。

   ![从贡献分析中排除维度](assets/excluding-dimensions.png)

1. 选择&#x200B;**[!UICONTROL 运行贡献分析]**。

1. 正在处理贡献分析，请稍候。 处理过程可能需要相当长的时间，具体取决于报表包的大小和维度的数量。 贡献分析对每个维度中的前50,000个项目执行分析。 您还会收到有关剩余[个贡献分析令牌](anomaly-detection.md#contribution-analysis-tokens)的通知。

   ![贡献分析正在执行](assets/contribution-analysis-executing.png)

1. Analysis Workspace直接在此项目中加载新的&#x200B;**[!UICONTROL 贡献分析]**&#x200B;面板。

   ![贡献分析面板](assets/contribution-analysis.png)

   * [摘要数字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)可视化图表。
   * 每月趋势[线](/help/analyze/analysis-workspace/visualizations/line.md)可视化。
   * 一个&#x200B;**[!UICONTROL 排名最前的项目]** [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，它按[贡献得分](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)排序，显示哪些排名最前的项目对该异常有贡献。 其他列显示相关量度，以及一个&#x200B;**[!UICONTROL 独特访客]**&#x200B;量度以提供上下文。

   * **[!UICONTROL 生成的区段（排名最前的项目群集）]** [自由格式表](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)根据贡献得分、异常发生次数和导致异常量度的总体百分比来识别排名最前的项目的关联。 然后，此关联将捕获为受众区段（贡献区段1、贡献区段2等）。 选择![信息](/help/assets/icons/Info.svg)以显示区段的定义，包括区段由哪些排名最前的项目组成：


1. 由于贡献分析现在是Analysis Workspace的一部分，因此您可以从自由格式表上下文菜单利用其许多功能来使您的分析更有意义，例如：

   * [按其他维度划分每个维度项](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [显示一个或多个行的趋势](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [添加新可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [创建警报](/help/components/c-alerts/intellligent-alerts.md)
   * [创建或比较区段。](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>在“贡献分析”和与之关联的“智能警报”项目中，分析出的异常以蓝色圆点突出显示。 此高亮显示可更清楚地指示正在分析的异常。


## 排除维度

您可能需要从贡献分析中排除某些维度。 例如，您可能根本不关心任何与浏览器或硬件相关的维度，因此希望删除它们从而加快分析速度。

要管理排除的维度，请执行以下操作：

* 将任何多余的维度拖到&#x200B;**[!UICONTROL 排除的维度]**&#x200B;面板中，然后单击&#x200B;**[!UICONTROL 设置为默认值]**&#x200B;保存列表。

* 选择&#x200B;**[!UICONTROL 全部清除]**&#x200B;以重新开始。

* 选择![维度](/help/assets/icons/Dimensions.svg)以显示上下文菜单，并使用![CrossSize400](/help/assets/icons/CrossSize400.svg)从列表中删除任何选定的排除维度。

  ![](assets/excluded-dimensions-list.png)

修改要排除的维度后，再次选择&#x200B;**[!UICONTROL 运行贡献分析]**。

