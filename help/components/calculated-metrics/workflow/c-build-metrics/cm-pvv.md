---
description: 了解如何构建简单的计算量度。
title: 构建简单的计算量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 0fbd80070051286f999af8eec9100f617cc498d5
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 17%

---

# 构建简单的计算量度

以下信息说明如何创建简单的&#x200B;*每次访问页面查看次数*&#x200B;指标。

1. 开始生成度量，如[生成度量](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)中所述。
1. 命名量度`Page Views per Visit`或类似名称。
1. 为量度提供用户友好的&#x200B;**[!UICONTROL 描述]**&#x200B;以显示该量度的用途。
1. 选择正确的&#x200B;**[!UICONTROL 格式]**。 对于此示例，请选择&#x200B;**[!UICONTROL 十进制]**。
1. 确定您希望报表显示多少个小数位。
1. 在&#x200B;**[!UICONTROL 将上升趋势显示为]**&#x200B;下拉菜单中，选择▲ **[!UICONTROL 良好（绿色）]**。
1. 添加&#x200B;**[!UICONTROL 标记]**&#x200B;以组织您的量度。
1. 对于此计算量度，首先将&#x200B;**[!UICONTROL 页面查看次数]**&#x200B;从&#x200B;**[!UICONTROL Metrics]**&#x200B;组件拖动到画布的&#x200B;**[!UICONTROL Definition]**&#x200B;部分。
1. 然后从&#x200B;**[!UICONTROL Metrics]**&#x200B;组件中拖动&#x200B;**[!UICONTROL 访问]**，并将指标放在&#x200B;**[!UICONTROL 页面查看次数]**&#x200B;下（等到显示蓝线之后再放置指标）。
1. 选择除![除](/help/assets/icons/Divide.svg)运算符。 （“除以”是默认的运算符。）
1. 生成量度时，您可以看到该量度的&#x200B;**[!UICONTROL 预览]**。
1. [产品兼容性](/help/components/calculated-metrics/cm-compatibility.md)显示量度是与“当前数据”兼容，还是只与“完全处理数据”兼容。

   ![简单计算量度](assets/simple-calculated-metric.png)
1. 选择&#x200B;**[!UICONTROL 保存]**。

   请注意，无论您何时对量度定义进行更改，**[!UICONTROL 概要]**&#x200B;公式都会随之发生更新。

1. （可选）要共享、批准、（重新）标记、重命名或删除指标，可转到[计算量度管理器](/help/components/calculated-metrics/workflow/cm-manager.md)。

