---
description: 创建具有嵌入请求的报表后，您可以通过在 Excel 中单击“文件”>“保存”或“文件”>“另存为”来保存报表。Report Builder 会检测报表是否包含请求。单击任一保存选项时，将显示“将工作簿另存为”窗体。
title: 保存具有请求的工作簿
uuid: 31611031-0982-4124-9fc7-7888124aa603
feature: Report Builder
role: User, Admin
exl-id: 192ac2f6-cfb8-447b-8fc1-19ad786ef924
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 100%

---

# 保存具有请求的工作簿

创建具有嵌入请求的报表后，您可以通过在 Excel 中单击“文件”>“保存”或“文件”>“另存为”来保存报表。Report Builder 会检测报表是否包含请求。单击任一保存选项时，将显示“将工作簿另存为”窗体。

* 根据使用 Windows 应用程序处理大量工作时的最佳做法，Adobe 建议您在电子表格中随时保存请求，以避免意外丢失工作表中的请求。
* 为工作簿命名时，请考虑在文件名中包含版本号，以便保存工作历史记录。例如，将第一个工作簿命名为 [!DNL web_forecast_01_01.xlsx]。
* 如果您已经保存过报表，则第二次保存报表时不会显示“[!UICONTROL 保存模板]”窗体。如果报表不包含请求，则不显示此对话框，而是显示标准 Excel“[!UICONTROL 另存为]”窗体。

## 文件名和位置 {#section_2406629E9B644CE08430826948977D5D}

[!UICONTROL 保存模板]窗体包含一些与标准 Excel [!UICONTROL 文件] > [!UICONTROL 另存为]对话框相同的功能，如用于输入电子表格报表的文件名（使用传统 [!DNL .xls] 文件扩展名）的文本框。

使用的任何文件名所包含的字符数不能超过 255 个。此外，文件名不能包含以下字符：

\ ? | > &lt; : / &#42; &#39; &quot;

最后，不能使用除扩展 ASCII 字符集之外的 Unicode 字符。

将文件保存到本地或网络驱动器上的某一位置时，您可以在文本框中输入完整路径，也可以单击[!UICONTROL 另存为]文本框旁边的浏览按钮 ![browse_button.gif](assets/browse_button.gif)。
