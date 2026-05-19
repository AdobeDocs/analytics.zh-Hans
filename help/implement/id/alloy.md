---
title: 使用Web SDK JavaScript库进行访客识别
description: 在实施Web SDK JavaScript库时正确识别访客。
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: https://experienceleague.adobe.com/R6O--qqR7SzlArrIDFCWunUEAduzmAS2Skm6BKyREnw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 2%

---

# 使用Web SDK JavaScript库进行访客识别

Adobe Experience Platform Web SDK JavaScript库(`alloy.js`)为所有Adobe CX Enterprise应用程序（包括Adobe Analytics）提供了一种统一的现代化数据收集方法。 虽然大多数客户通常实施[Web SDK标记扩展](web-sdk-extension.md)，但您可以自行或在第三方标记管理系统中使用Web SDK JavaScript库。 请参阅GitHub上的[Alloy](https://github.com/adobe/alloy)以下载最新版本的库。

可以使用XDM的`identityMap`扩展身份数据以支持自定义ID和多个命名空间。 Adobe建议将Adobe Experience Cloud ID服务用作Analytics的主要标识符，并将其他身份管理选项用于高级方案。

如果您的组织使用Web SDK JavaScript库将数据发送到Adobe Analytics，则访客识别需要最少的配置。 访客ID服务以本机方式驻留在库中，仅要求您在`configure`命令中设置&#x200B;**[!UICONTROL Edge域]**。 如果此字段设置为所需的值，则访客标识无需任何其他配置即可正常工作。
