---
description: 您可以在 Analysis Workspace 中从接触点创建区段、添加区段作为接触点，并比较多个区段之间的关键工作流程。
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: 在流失分析中应用区段
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 在流失分析中应用区段

您可以在 Analysis Workspace 中从接触点创建区段、添加区段作为接触点，并比较多个区段之间的关键工作流程。

>[!IMPORTANT] 用作流失中检查点的区段必须使用级别低于流失可视化图表整体上下文的容器。对于访客上下文流失，用作检查点的区段必须是基于访问或基于点击的区段。对于访问上下文流失，用作检查点的区段必须是基于点击的区段。如果您使用的组合无效，则流失率将为 100%。我们为流失可视化图表添加了警告，当您添加不兼容的区段作为接触点时，将显示该警告。某些无效的区段容器组合会导致无效的流失图表，例如：

* 在访客上下文流失可视化图表中使用基于访客的区段作为接触点
* 在访问上下文流失可视化图表中使用基于访客的区段作为接触点
* 在访问上下文流失可视化图表中使用基于访问的区段作为接触点

## 从接触点创建区段 {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 从特定的接触点创建一个您特别感兴趣，并且可以应用至其他报表的区段。为此，请右键单击触点并选择 **[!UICONTROL Create segment from touchpoint]**。

   ![](assets/segment-from-touchpoint.png)

   此时会打开区段生成器，其中预先填充了与所选触点匹配的顺序区段：

   ![](assets/segment-builder.png)

1. 为区段提供标题和说明并保存它。

   您现在可以在任何您需要的报告中使用此区段。

## 添加区段作为接触点 {#section_17611C1A07444BE891DC21EE8FC03EFC}

例如，如果您想了解您的美国用户如何趋势化和影响流失，只需将美国用户细分拖入流失：

![](assets/segment-touchpoint.png)

或者，您也可以通过将美国用户区段拖动到另一个检查点来创建AND触点。

## 在流失中比较区段 {#section_E0B761A69B1545908B52E05379277B56}

您可以在流失可视化中比较不限数量的细分。

1. 从左边的边栏中选择要比较 [!UICONTROL Segments] 的区段。 在我们的示例中，我们选择了2个区段：美国用户和非美国用户。
1. 将它们拖入顶部的区段拖放区。

   ![](assets/segment-drop.png)

1. 可选：您可以保留“所有访问”作为默认容器或删除它。

   ![](assets/seg-compare.png)

1. 您现在可以比较两个细分的流失情况，如一个细分的表现优于另一个细分，或其他洞察。
