---
description: 与复制并粘贴请求一样，您还可以通过从快捷菜单中选择“剪切请求”将请求重定位到电子表格的其他位置。
title: 复制相邻请求
topic: Report builder
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 复制相邻请求

与复制并粘贴请求一样，您还可以通过从快捷菜单中选择“剪切请求”将请求重定位到电子表格的其他位置。

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. 如果您在剪切某一特定请求后改变了主意，决定复制或剪切另一单元格中的其他请求，Report Builder 会将第一个请求保留在其原单元格中，仅对第二个请求执行操作（复制或剪切）。

>[!NOTE]对于剪切或粘贴请求，Report Builder 不支持 Excel 的“撤消”命令。因此，在剪切请求时一定要谨慎。

您不一定要在工作簿的同一工作表中复制并粘贴。您可以复制一个工作表中的请求，然后粘贴到同一工作簿中另一工作表的某个位置。

您不一定要一次复制并粘贴一个请求。您可以选择电子表格中的多个请求，然后将这些请求粘贴到电子表格的空白区域。与复制并粘贴一个请求一样，请确保粘贴区域中的单元格不包含请求，否则粘贴操作会替换这些请求。If the system finds that the target paste region already contains one or more requests, report builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. 必须选择其他单元格作为粘贴操作的目标位置，以便请求不会重叠。
