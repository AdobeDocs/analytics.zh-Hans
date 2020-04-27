---
description: 向请求添加量度和维度的步骤。
title: 添加量度和维度
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 添加量度和维度

向请求添加量度和维度的步骤。

1. [在上创建数据请求](/help/analyze/report-builder/data-requests/data-requests.md) , [!UICONTROL Request Wizard: Step 1]然后单击 **[!UICONTROL Next]**。
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![步骤信息](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. 例如，除了每个值外，您还可以显示量度小计。然而，每次添加或删除维度时，可用量度列表都会发生变化。

   You can add only metrics to the [!UICONTROL Metrics] layout section. 将量度添加到布 [!UICONTROL Column Label] 局中作为 [!UICONTROL Metric Header]。 If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   请注意，在“量度”选项卡中的“量度”列表正上方会显示搜索栏。

   ![](assets/search_bar_metric.png)

   请牢记这一点：

   * 当输入搜索词时，列表将自动更新，只显示标签与搜索词相匹配的量度。
   * 匹配不区分大小写，等同于“包含”搜索。
   * 不支持全词搜索或其他特定的搜索标记（“以...开始”、“以...结束”、“和”、“或”等）。

      如果退出请求向导（即单击“完成”或“取消”）、返回请求向导的第 1 步或者更改量度类别，那么搜索词将被清除。

      在下列情况中，搜索词不会被清除：

   * 从列表中拖放（或双击）一个量度项目，以将其添加到引导布局/自定义布局量度面板。
   * 从引导布局/自定义布局量度面板删除一个量度项目。
   * 单击“维度”选项卡，然后返回“量度”选项卡。
   * 在退出时调用其他子表单（模式或非模式）将会返回到请求向导的第 2 步。这些表单的示例包括

      * 维度过滤器表单
      * 日期范围格式表单
      * 格式选项表单
      * 前置-后置文本表单
      * 输出范围位置表单

1. （可选）要按量度排列请求，只需单击量度标签即可。
1. 使用与添加量度相同的方法添加维度。

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. 将维度放到布局网格时，会将其从树视图中删除，并重新计算剩余可用维度的列表。

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. 有效值为：

    * 小时
    * 日
    * 周
    * 月
    * 年
    * 日期范围（未指定粒度时）

1. 通过配置[格式选项](/help/analyze/report-builder/layout/t-format-display-headers.md)和过滤器，修改量度和维度。
1. 单击 **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. 此处，维 [!UICONTROL Referring Domain] 度将在和之间创建细分 [!UICONTROL Page] 报告 [!UICONTROL Referring Domain]。 The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)
