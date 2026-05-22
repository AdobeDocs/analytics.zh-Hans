---
description: 了解如何保存包含嵌入请求的报表。
title: 关于保存带有请求的工作簿
uuid: 31611031-0982-4124-9fc7-7888124aa603
feature: Report Builder
role: User, Admin
exl-id: 192ac2f6-cfb8-447b-8fc1-19ad786ef924
TQID: https://experienceleague.adobe.com/0UMDDWbeilsUp-yB-tzMVcWkGfUXtf4lh2ciaAg4AEk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 31%

---

# 保存具有请求的工作簿

{{legacy-arb}}

创建包含嵌入请求的报表时，可以在Excel中使用&#x200B;**文件** > **保存**&#x200B;或&#x200B;**文件** > **另存为**&#x200B;保存这些报表。 Report Builder检测报表是否包含请求。 选择其中一个保存选项后，请完成&#x200B;**将工作簿另存为**&#x200B;表单。

* 作为使用Windows应用程序进行大量工作的最佳实践，Adobe建议您经常定期将请求保存在电子表格中，以避免在工作表中意外丢失请求。
* 在命名工作簿时，请考虑在文件名中使用版本号，以便可以保留工作历史记录。 例如，将第一个工作簿命名为 [!DNL web_forecast_01_01.xlsx]。
* 如果已保存报告，则在再次保存报告时，不会显示[!UICONTROL 保存模板]表单。 如果报告不包含请求，则不会显示此对话框。 而是显示标准Excel [!UICONTROL 另存为]表单。

## 文件名和位置 {#section_2406629E9B644CE08430826948977D5D}

[!UICONTROL 保存模板]窗体包含一些与标准 Excel [!UICONTROL 文件] > [!UICONTROL 另存为]对话框相同的功能，如用于输入电子表格报表的文件名（使用传统 [!DNL .xls] 文件扩展名）的文本框。

您使用的任何文件名都必须包含255个或更少的字符。 此外，文件名不能包含以下字符：

\ ? | > &lt; : / &#42; &#39; &quot;

最后，不能使用超出扩展ASCII字符集的Unicode字符。

将文件保存到本地或网络驱动器上的某一位置时，您可以在文本框中输入完整路径，也可以单击[!UICONTROL 另存为]文本框旁边的浏览按钮 ![browse_button.gif](assets/browse_button.gif)。
