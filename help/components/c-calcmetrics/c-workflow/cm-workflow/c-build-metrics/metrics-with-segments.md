---
description: 通过为个别指标分段，可在同一报表中比较各个指标。
title: 分段指标
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 68%

---

# 分段指标

在计算指标生成器中，可在指标定义中应用区段。如果要推导新指标以便在分析中使用，则这样做很有帮助。请记住，可通过区段生成器更新区段定义。如果作出了更改，则区段将在任何应用它的地方自动更新，其中包括它是否为计算指标定义的一部分。

![](assets/german-visitors.png)

## 创建分段指标 {#create}

比如要比较“德国访客”区段的不同方面与“国际访客”区段的不同方面。您可以创建指标为您提供如下分析：

* 两个群组之间的内容浏览行为是如何比较的？（另一个示例为：两个区段之间的转化率是如何比较的？）
* 浏览某些页面的德国访客与国际访客各占总访客数的多少百分比？
* 在这些不同的区段访问哪些内容方面，最大的区别是什么？

生成并保存名为“德国访客”的量度和名为“国际访客”的量度：

1. 在计算量度生成器中创建一个名为“德国访客”的临时区段，其中“国家/地区”等于“德国”。

   将“国家/地区”维度拖到“定义”画布中，并选择&#x200B;[!UICONTROL **Germany**]&#x200B;作为值：

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >也可在[区段生成器](/help/components/segmentation/segmentation-workflow/seg-build.md)中这样做，但我们已通过在计算量度生成器中提供维度而简化了该工作流程。 “临时”表示该区段在左边栏中的&#x200B;**[!UICONTROL “区段”]**&#x200B;列表中不可见。但是，您可以将鼠标悬停在该列表旁边的“i”图标上，然后单击&#x200B;**[!UICONTROL 设为公用]**。

1. 将“德国”区段拖到“定义”画布中，并将“独特访客”量度拖动到其中：

   ![](assets/german-visitors.png)

1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;以保存计算量度。

1. 在计算量度生成器中创建一个名为“国际访客”的临时区段，其中“国家/地区”不等于“德国”。

   将“国家/地区”维度拖入“定义”画布，选择&#x200B;[!UICONTROL **Germany**]&#x200B;作为值，然后选择&#x200B;[!UICONTROL **does not equal**]&#x200B;作为运算符。

1. 将独特访客指标拖动到其中。

1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;以保存计算量度。

1. 在 Analysis Workspace 中，将&#x200B;**[!UICONTROL 页面]**&#x200B;维度拖动到自由格式表中，并将两个新的计算指标拖动到顶部且使它们彼此相邻：

   ![](assets/workspace-pages.png)


>[!BEGINSHADEBOX]

有关演示视频，请参阅![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [分段量度](https://video.tv.adobe.com/v/37925?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


## 占总指标的百分比 {#percent-total}

对于上述示例，可更进一步比较您的区段与总人口。为此，请创建两个新指标，“德国访客总数的百分比”和“国际访客总数的百分比”：

1. 将德国（或国际）访客区段拖放到画布中。
1. 将另一个德国（或国际）访客区段拖放到下方。但这一次，请单击其配置（齿轮）图标以选择指标类型“合计”。格式应当为“百分比”。运算符应当为“除以”。您最终会获得以下指标定义：

   ![](assets/cm_metric_total.png)

1. 将此指标应用于您的项目：

   ![](assets/cm_percent_total.png)
