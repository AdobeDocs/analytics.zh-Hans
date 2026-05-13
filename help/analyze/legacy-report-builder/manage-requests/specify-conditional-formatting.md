---
description: 了解如何将条件格式应用到工作簿单元格。
title: 关于工作簿的条件格式
uuid: 13ac12f1-3498-4bf9-a6d0-c5d84e0125dc
feature: Report Builder
role: User, Admin
exl-id: 5a5f2415-8269-4c8a-9193-784537b29edf
TQID: https://experienceleague.adobe.com/UnZqnq2Y3D7AfZ6mM0xNVVr4F-wOKhqix4tTTo6BQg0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 175
ht-degree: 7%

---

# 指定条件格式

{{legacy-arb}}

创建具有嵌入请求的报表后，可以对工作簿单元格应用条件格式。

在Report Builder工具栏上，单击&#x200B;**[!UICONTROL 格式]**。

条件格式设置允许您标识包含要监视的结果或值的单元格。 例如，如果收入低于预期值，您可以对特定单元格应用红色阴影或高亮显示；如果收入超过您预测的金额，则可以应用蓝色阴影。 如果请求的日期范围更改删除了导致条件格式应用于单元格值的条件，则突出显示该条件的格式将暂时禁用。 如果指定的条件格式因不符合条件而不发生更改，则这些条件格式将继续应用于单元格，直到您将其删除为止。

出于安全原因，如果您使用Excel的Visual Basic for Applications (VBA)语言编写工作簿宏，则会禁用宏。

>[!NOTE]
>
>条件格式是Excel的一项功能。 有关创建格式规则的信息，请参阅 Excel 文档。
