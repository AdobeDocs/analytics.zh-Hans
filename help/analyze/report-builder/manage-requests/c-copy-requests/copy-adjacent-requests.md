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

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. 如果您在剪切特定请求后改变了主意，决定复制或剪切其他单元格的其他请求，Report Builder会将第一个请求保留在其原始单元格中，只对第二个请求执行操作（复制或剪切）。

>[!NOTE]对于剪切或粘贴请求，Report Builder 不支持 Excel 的“撤消”命令。因此，在切断请求时要小心。

您不仅可以复制并粘贴到工作簿的同一工作表中。 您可以将请求复制到一张工作表中，然后粘贴到同一工作簿的另一张工作表中的位置。

您不仅可以一次复制并粘贴一个请求。 您可以在电子表格中选择多个请求并将其粘贴到电子表格的空区域。 就像复制和粘贴一个请求一样，请确保粘贴区域没有包含将由粘贴操作替换的请求的单元格。 如果系统发现目标粘贴区域已包含一个或多个请求，则报表生成器不会显示任何复制或剪切 [!UICONTROL Paste Requests] 的请求的菜单。 必须选择其他单元格作为粘贴操作的目标，这样请求就不会重叠。
