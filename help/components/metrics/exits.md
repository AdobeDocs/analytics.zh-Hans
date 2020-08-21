---
title: 退出
description: 访问中最后一个值的实例。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 68%

---


# 退出

*此帮助页介绍了“退出”如何充当量度。有关“退出”如何充当维度的信息，请参阅[退出维度](../dimensions/exit-dimensions.md)。*

“退出”度量显示给定维度项目作为访问中最后一个值被捕获的次数。 当您想进一步了解访客离开网站前最后看到的内容时，此量度非常有用。查看维度的最后值，有助于您了解和优化访客在离开网站前获得的体验。

## 如何计算此量度

After a [visit](visits.md) concludes, record the most recent dimension item as an exit. 每次访问的每个维度只存在一个退出。如果在以前的点击中设置了维度，则它不一定是访问的最后一次点击。它是一个基于访问的量度；它可追溯应用于访问中的所有点击。

>[!TIP]
>
>如果您针对并非每次访问都设置的维视图此度量，则可以在Analysis Workspace隐藏“未指定”维项。 单击过滤器图标，然后取消选中[!UICONTROL 包含未指定项（无）]。
