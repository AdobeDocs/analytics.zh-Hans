---
description: 了解维度间流量如何让您检查各种维度之间的用户路径。
title: 维度间流量
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
TQID: https://experienceleague.adobe.com/9OjAFYHo5uhcfbQQOB46jfG1R2wIQCBHXEr842EcZQ0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 95%

---

# 维度间流量

通过维度间流量可以跨不同维度查看用户路径。

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inter-dimensional flows](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

本文展示了如何在两种用例中使用此流量：移动应用程序交互和事件，以及营销活动如何推动 Web 访问次数。

## 移动应用程序交互和事件

此示例流量中使用[!UICONTROL 屏幕名称]维度来查看用户如何使用应用程序中的各种屏幕（场景）。 返回的顶部屏幕为 **[!UICONTROL luma: content: ios: en: home]**，即应用程序的主页：

![显示已添加项目的流量。](assets/flowapp.png)

要浏览此应用程序中屏幕和事件类型（如添加到购物车、购买等）之间的交互，请拖放&#x200B;**[!UICONTROL 事件类型]**&#x200B;维度：

* 在流量中任何可用步骤的顶部，替换该维度：

  ![显示将页面维度拖到多个区域的流量。](assets/flowapp-replace.png)

* 在当前流量可视化图表之外添加维度：

  ![显示将页面维度拖到末端空白处的流量。](assets/flowapp-add.png)

下面的流量可视化图表显示了添加&#x200B;**[!UICONTROL 事件类型]**&#x200B;维度的结果。 该可视化图表可让您洞察移动应用程序用户在将产品添加到购物车、关闭应用程序、展现产品建议等之前是如何在应用程序的各个屏幕之间移动的。

![显示将页面维度结果展现在列表顶部的流量。](assets/flowapp-result.png)

## 营销活动如何推动 Web 访问次数

您想要分析哪些营销活动可以推动网站访问次数。 您可以使用&#x200B;**[!UICONTROL 营销活动名称]**&#x200B;作为维度创建流量可视化图表

![流量 Web 营销活动名称维度](assets/flowweb.png)

您可以用&#x200B;**[!UICONTROL 格式化页面名称]**&#x200B;维度替换最后一个&#x200B;**[!UICONTROL 营销活动名称]**&#x200B;维度，并在流量可视化图表的末端添加另一个&#x200B;**[!UICONTROL 格式化页面名称]**&#x200B;维度。

![流量 Web 营销活动名称和 Web 页面维度](assets/flowweb-replace.png)

您可以将光标悬停在任意流量上，以查看更多详细信息。 例如哪些营销活动导致了购物车结账。

![流量 Web 营销活动名称和 Web 页面悬停](assets/flowweb-hover.png)
