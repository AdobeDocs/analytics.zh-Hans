---
description: 创建具有嵌入请求的报表后，您可以通过在 Excel 中单击“文件”>“保存”或“文件”>“另存为”来保存报表。Report Builder 会检测报表是否包含请求。单击任一保存选项时，将显示“将工作簿另存为”窗体。
title: 保存具有请求的工作簿
topic: Report builder
uuid: 31611031-0982-4124-9fc7-7888124aa603
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 保存具有请求的工作簿

创建具有嵌入请求的报表后，您可以通过在 Excel 中单击“文件”>“保存”或“文件”>“另存为”来保存报表。Report Builder 会检测报表是否包含请求。单击任一保存选项时，将显示“将工作簿另存为”窗体。

* 根据使用 Windows 应用程序处理大量工作时的最佳做法，Adobe 建议您在电子表格中随时保存请求，以避免意外丢失工作表中的请求。
* 为工作簿命名时，请考虑在文件名中包含版本号，以便保存工作历史记录。例如，将第一个工作簿命名为 [!DNL web_forecast_01_01.xlsx]。
* If you have already saved the report, the [!UICONTROL Save Template] form is not displayed when saving the report a second time. 如果报表不包含请求，则不显示此对话框，Instead, the standard Excel [!UICONTROL Save As] form is displayed.

## 文件名和位置 {#section_2406629E9B644CE08430826948977D5D}

The [!UICONTROL Save Template] form has some of the same functions as the standard Excel [!UICONTROL File] > [!UICONTROL Save As] dialog box, such as a text box for entering the file name of the spreadsheet report using the conventional [!DNL .xls] file extension.

使用的任何文件名所包含的字符数不能超过 255 个。此外，文件名不能包含以下字符：

\ ? | > &lt; : / * &#39; &quot;

最后，不能使用除扩展 ASCII 字符集之外的 Unicode 字符。

When saving the file to a location on your local or network drives, you may enter the full path in the text box, or click on the browse button  ![browse_button.gif](assets/browse_button.gif) adjacent to the [!UICONTROL Save As] text box.
