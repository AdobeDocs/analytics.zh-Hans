---
description: '对单个量度分段允许您对同一报表内的量度进行比较。 '
title: 分段量度
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: 234a2eadfe02322daa886d2edbea042f8ad99e1e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 59%

---


# 分段量度

在“计算的量度生成器”中，您可以在度量定义中应用区段。 如果您想要导出要在分析中使用的新指标，此功能非常有用。 请记住，区段定义可通过区段生成器进行更新。 如果进行了更改，则区段将在应用时自动更新，包括它是计算度量定义的一部分时。

![](assets/german-visitors.png)

## 创建分段度量 {#create}

假设您要比较“德国访客”细分与“国际访客”细分的不同方面。 您可以创建量度为您提供如下分析：

* 两个群组之间的内容浏览行为是如何比较的？（另一个示例为：两个区段之间的转化率是如何比较的？）
* 与国际访客相比，德国访客浏览特定页面的比例是多少？
* 在这些不同区段所访问的内容方面，存在的最大差别是什么？

1. 如果您没有可比较的区段，请在计算量度生成器中创建一个名为“德国访客”的临时区段，其中“国家”等于“德国”。 将“国家/地区”维度拖动到“定义”画布中，并选择“德国”作为值：

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >您也可以在[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)中执行此操作，但是我们已在计算量度生成器中提供了维度，从而简化了工作流程。&quot;Adhoc&quot; means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. 但是，您可以将鼠标悬停在该列表旁边的“i”图标上，然后单击&#x200B;**[!UICONTROL 设为公用]**。

1. 如果您没有可比较的区段，请创建一个名为“国际访客”的区段，其中“国家/地区”不等于“德国”。
1. 通过将“德国”区段拖到“定义”画布中，并将独特访客量度拖到其内部，生成并保存名为“德国访客”的量度。

   ![](assets/german-visitors.png)

1. 对国际访客区段和独特访客量度重复执行步骤 3，以便创建“国际访客”量度。
1. 在 Analysis Workspace 中，将&#x200B;**[!UICONTROL 页面]**&#x200B;维度拖动到自由格式表中，并将两个新的计算量度拖动到顶部且使它们彼此相邻：

   ![](assets/workspace-pages.png)

## 总指标的百分比 {#percent-total}

您可以通过比较区段与总人口，进一步了解上面的示例。 为此，请创建两个新指标：“德国访客总数的%”和“国际访客总数的%”:

1. 将德国（或国际）访客区段拖放到画布中。
1. 将另一个德国（或国际）访客区段拖放到下方。但这一次，请单击其配置（齿轮）图标以选择量度类型“合计”。格式应当为“百分比”。运算符应当为“除以”。您最终会获得以下量度定义：

   ![](assets/cm_metric_total.png)

1. 将此量度应用于您的项目：

   ![](assets/cm_percent_total.png)

