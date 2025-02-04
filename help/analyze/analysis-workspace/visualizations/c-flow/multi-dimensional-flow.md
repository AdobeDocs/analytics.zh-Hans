---
description: 通过维度间流量可以跨不同维度查看用户路径。
title: 维度间流量
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 7%

---

# 维度间流量

通过维度间流量可以跨不同维度查看用户路径。

>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [维度间流量](https://video.tv.adobe.com/v/24041?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

本文介绍了如何将此流用于两个用例：移动应用程序交互和事件，以及营销活动如何推动Web访问。

## 移动应用程序交互和事件

在此示例流中使用[!UICONTROL 屏幕名称]维度，以了解用户如何在应用程序中使用各种屏幕（场景）。 返回的上部屏幕为&#x200B;**[!UICONTROL luma： content： ios： en： home]**，这是应用程序的主页：

![显示已添加项目的流量。](assets/flowapp.png)

要浏览此应用中的屏幕与事件类型（如添加到购物车、购买及其他）之间的交互，请拖放&#x200B;**[!UICONTROL 事件类型]**&#x200B;维度：

* 在流中任何可用步骤的顶部，替换该维度：

  ![显示拖到多个区域的“页面”维度的流量。](assets/flowapp-replace.png)

* 在当前流量可视化图表之外，要添加维度：

  ![一个显示页面维度的流程，该流程在结尾被拖到空白处。](assets/flowapp-add.png)

下面的流量可视化显示了添加&#x200B;**[!UICONTROL 事件类型]**&#x200B;维度的结果。 该可视化图表提供了有关移动设备应用程序用户在向购物车添加产品、关闭应用程序、提供选件等操作之前如何在应用程序中的各个屏幕中进行移动的分析。

在列表顶部显示“页面”维度结果的![法郎。](assets/flowapp-result.png)

## 营销活动如何推动Web访问

您要分析哪些营销活动促使访问网站。 创建以&#x200B;**[!UICONTROL 促销活动名称]**&#x200B;为维度的流量可视化图表

![流量Web促销活动名称维度](assets/flowweb.png)

您将最后的&#x200B;**[!UICONTROL 促销活动名称]**&#x200B;维度替换为&#x200B;**[!UICONTROL 格式化的页面名称]**&#x200B;维度，并在流量可视化图表的末尾添加另一个&#x200B;**[!UICONTROL 格式化的页面名称]**&#x200B;维度。

![流量Web促销活动名称和网页维度](assets/flowweb-replace.png)

您可以将鼠标悬停在任何流上以查看更多详细信息。 例如，哪些营销活动导致了购物车结账。

![流Web促销活动名称和网页维度悬停](assets/flowweb-hover.png)
