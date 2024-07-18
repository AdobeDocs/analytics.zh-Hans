---
description: 有关如何创建量度以显示哪个营销渠道有助于提高订购数量的说明。此说明适用于任何感兴趣的维度或成功事件。
title: 订购协助量度
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 59%

---

# 生成“订单协助”量度

以下信息说明了如何创建量度，以显示哪些营销渠道有助于推动订单。 此说明适用于任何感兴趣的维度或成功事件。

1. 开始创建计算量度，如[生成量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)中所述。

1. 在计算量度生成器中，将量度命名为“辅助订单”或类似名称。

1. 在“定义”画布中，拖入“订购”量度。然后，选中&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;复选框，以通过“设置”齿轮调整归因模型。

   ![](assets/attr-model.png)

1. 选择&#x200B;**[!UICONTROL 自定义]**&#x200B;作为归因模型。将权重更改为 0（首次接触），100（中间接触）和 0（最后接触）。

   ![](assets/custom-attr-model.png)

1. 选择&#x200B;[!UICONTROL **应用**] > [!UICONTROL **保存**]。

1. 在Analysis Workspace中，创建一个具有营销渠道维度、订单和您的新辅助订单量度的自由格式表。

   ![](assets/mktg-channel-assists.png)

   这种方法可轻松显示哪些营销渠道有助于提高订购数量。或者，在自由格式表中，您可以右键单击任意量度并直接从表中调整归因模型。

1. （可选）与组织中的其他用户共享该量度，如[共享计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)中所述。
