---
description: 'null'
title: 运行贡献分析
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 运行贡献分析

贡献分析是一个密集的机器学习过程，旨在发现Adobe Analytics中观察到的异常的贡献者。 其目的是帮助用户以比其他可能更快的速度找到重点或机会进行额外分析。

## 运行贡献分析 {#section_7D2C5E48A5664727941DF4C90976D9DC}

在项目中可以通过两种方式来调用贡献分析：

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. 甚至可以对没有显示任何异常的行运行贡献分析。

   >[!NOTE]
   >
   >我们当前仅支持对每天粒度进行贡献分析。

   ![](assets/run_ca.png)

* 在折线图中，将光标悬停在折线图中的异常数据点上。Click the **[!UICONTROL Analyze]** link that appears.

   ![](assets/contribution-analysis.png)

1. (Optional) After you have clicked **[!UICONTROL Run Contribution Analysis]** in either the line chart or a table, you can narrow the scope of (and thus speed up) the analysis by [excluding dimensions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. 等待您的贡献分析加载。 这可能需要相当长的时间，具体取决于报表包的大小和维数。 贡献分析对每个维度前50,000个项目执行分析。
1. 分析工作区随后会直接在此项目中加载新的贡献分析面板。 如果您之前在Reports &amp; Analytics中使用过贡献分析，您会注意到许多熟悉的面板：

   * 显示当天访问次 **数** 的可视化。
   * 上下文的 **月度访问趋势** 线。
   * **促成此异常的热门项目** ，按贡献得分排序 [](https://marketing.adobe.com/resources/help/zh_CN/analytics/contribution/ca_contribution_score.html)，加上相关的量度，以及从大小调整角度将该量度放在上下文中的唯一访客量度。

   * “生 [成的区段](https://marketing.adobe.com/resources/help/zh_CN/analytics/contribution/ca_workflow_premium.html) （顶级项目群集）”表基于贡献得分、异常发生次数和对异常度量的贡献总百分比来标识顶级项目的关联。 然后，此区段会作为受众区段（贡献区段1、贡献区段2等）捕获。 单击“i”（信息）按钮将为您提供每个自动区段的定义的视图，包括它由哪些顶级项目组成：

      ![](assets/auto_segment.png)

1. 由于贡献分析现在是分析工作区的一部分，您可以从表格的右键单击菜单中充分利用其许多功能，使分析更有意义，例如：

   * [按其他维度划分每个维度项目。](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [显示一个或多个行的趋势。](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [添加新的可视化。](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [创建警报。](/help/components/c-alerts/intellligent-alerts.md)
   * [创建或比较区段。](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE] 在“贡献分析”和与之关联的“智能警报”项目中，我们使用蓝色圆点突出显示正在分析的异常。这样可以更清楚地指示正在分析的异常。

## 从贡献分析中排除维度 {#section_F6932F4BF74544B5872164E7B1E0C6FC}

有时您可能希望从贡献分析中排除某些维。 例如，您可能根本不关心任何与浏览器或硬件相关的维度，并且希望通过删除它们来加快分析。

1. 单击(或在折 **[!UICONTROL Run Contribution Analysis]** 线图 **[!UICONTROL Analyze]** 中)后，将显示 **[!UICONTROL Excluded Dimensions]** 面板。

1. 只需将任何不需要的尺寸拖 **[!UICONTROL Excluded Dimensions]** 入面板，然后单击以保存列表 **[!UICONTROL Set as Default]**。 Or, click **[!UICONTROL Clear All]** to start over with selecting dimensions to exclude.

   ![](assets/exclude_dimensions.png)

1. After you have added dimensions to exclude (or chosen not to), click **[!UICONTROL Run Contribution Analysis]** again.
1. 如果您需要修订排除的维度列表，只需双击“维度”，系统便会显示排除的维度列表：

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

