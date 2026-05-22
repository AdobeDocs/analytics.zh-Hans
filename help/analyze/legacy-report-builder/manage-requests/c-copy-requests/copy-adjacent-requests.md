---
description: 了解如何将请求复制、粘贴和重新定位到电子表格的其他部分。
title: 如何复制相邻请求
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
TQID: https://experienceleague.adobe.com/q1uVTribovAk-NJRXuAjW-kUIQfpquEPIbbOM9W8UmY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 8%

---

# 复制相邻请求

{{legacy-arb}}

与复制并粘贴请求一样，您还可以通过从快捷菜单中选择[!UICONTROL 剪切请求]将请求重新定位到电子表格的其他部分。

剪切请求会将请求从原位置删除，并在选择“[!UICONTROL 粘贴请求]”后将请求放置到新位置。 如果在剪切特定请求后改变主意，并决定复制或剪切其他单元格中的其他请求，Report Builder会将第一个请求保留在原始单元格中，并仅对第二个单元格执行操作（复制或剪切）。

>[!NOTE]
>
>对于剪切或粘贴请求，Report Builder不支持Excel的“撤消”命令。

您不仅可以在工作簿的同一工作表中复制和粘贴。 您可以复制一个工作表中的请求，并将其粘贴到同一工作簿中另一个工作表中的某个位置。

您并非只能一次复制和粘贴一个请求。 您可以在电子表格中选择多个请求，然后将它们粘贴到电子表格的空白区域。 与复制和粘贴一个请求一样，请确保粘贴区域没有单元格包含将被粘贴操作替换的请求。 如果系统发现目标粘贴区域已包含一个或多个请求，则Report Builder不显示任何复制或剪切请求的[!UICONTROL 粘贴请求]菜单。 您必须选择其他单元格作为粘贴操作的目标，以便请求不会重叠。
