---
description: 了解将量度和维度添加到请求的步骤。
title: 如何添加量度和维度
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
TQID: https://experienceleague.adobe.com/nKf59WLxvtYrcyR-mQ8oM41rUDLl3qpkwbujRDBV27A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 7%

---

# 添加量度和维度

{{legacy-arb}}

向请求添加量度和维度的步骤。

1. 使用[!UICONTROL 请求向导：第1]步表单来[创建数据请求](/help/analyze/legacy-report-builder/data-requests/data-requests.md)，然后单击&#x200B;**[!UICONTROL 下一步]**。
1. 在“[!UICONTROL 请求向导：第2]步”窗体中，双击量度，或将其拖动到所需位置。

   ![显示“请求向导：第2步”的屏幕截图，其中包含从量度列表指向所需页面查看部分的箭头。](assets/adding_metrics.png)

   添加量度时，不会从[!UICONTROL 量度]选项卡中删除这些量度，因为您可以在一个请求中多次显示量度。 例如，您可以显示指标小计以及每个值。 但是，每次添加或删除维度时，可用量度的列表都会发生更改。

   您只能将量度添加到[!UICONTROL 量度]布局部分。 度量作为[!UICONTROL 度量标题]添加到[!UICONTROL 列标签]布局中。 如果将[!UICONTROL 量度标题]从[!UICONTROL 列布局]移动到[!UICONTROL 行布局]，则它将显示在此处，并用作划分的量度。

   请注意，搜索栏显示在“量度”选项卡中“量度”列表的正上方。

   ![显示量度搜索栏的屏幕截图。](assets/search_bar_metric.png)

## 准则

添加量度和维度时，请考虑以下准则。

* 输入搜索词时，列表会自动更新以显示标签与搜索词匹配的量度。
* 匹配项不区分大小写，等同于&#x200B;*包含*&#x200B;搜索。
* 全字搜索和其他特殊搜索标志（开头为、结尾为、AND和OR等） 不受支持。

如果您在单击[!UICONTROL 完成]或[!UICONTROL 取消]后退出“请求向导”，或者返回到“请求向导”第1步，或者更改“量度”类别，搜索词将被清除。

未清除搜索词：

* 当您从列表中拖放（或双击）某个量度项，以便将其添加到“引导布局”/“自定义布局量度”面板时。
* 从“引导布局”/“自定义布局量度面板”中删除量度项时。
* 单击Dimension选项卡后，返回到“指标”选项卡。
* 当您调用其他子表单（模式或无模式）时，这些表单在退出时将返回到“请求向导”步骤2。 这些表单的示例包括

   * Dimension筛选器Forms
   * 日期范围格式Forms
   * 设置选项表单格式
   * 前置后置文本表单
   * 输出范围位置表单

## 按指标对请求排序

您可以选择按量度对请求进行排序。

要按指标对请求进行排序，请执行以下操作

1. 单击量度标签。
1. 添加维度。 使用与添加量度相同的方式添加维度。 请参阅上述步骤1和2。

   在[!UICONTROL 维度]选项卡上，系统显示划分维度，或作为您在[!UICONTROL 请求向导：第1]步以及报表包配置中选择的任何基础报表的分类。 将维拖放到布局网格中时，该维将从树视图中移除，并重新计算剩余可用维的列表。

   [!UICONTROL Date]维度将自动添加。 可用的日期维度会根据[!UICONTROL 请求向导：第1]步中选择的粒度而发生更改。 有效值为：

   * 小时
   * 日
   * 周
   * 月
   * 年
   * 日期范围（未指定粒度时）

1. 通过配置[格式选项](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md)和过滤器，修改量度和维度。
1. 单击&#x200B;**[!UICONTROL 完成]**。
在以下示例中，维度与“[!UICONTROL 页面]”量度相关联。 [!UICONTROL 反向链接域]维度将创建介于[!UICONTROL 页面]和[!UICONTROL 反向链接域]之间的划分报表。 [!UICONTROL Dimension]选项卡已更新，其中仅包含可添加到划分报表的维度。

   ![显示与量度相关的维度的屏幕截图。](assets/page_pageview_02.png)
