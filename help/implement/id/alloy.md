---
title: 使用Web SDK JavaScript库进行访客识别
description: 在实施Web SDK JavaScript库时正确识别访客。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# 使用Web SDK JavaScript库进行访客识别

Adobe Experience Platform Web SDK JavaScript库(`alloy.js`)为所有Adobe Experience Cloud应用程序(包括Adobe Analytics)提供了统一的现代化数据收集方法。 虽然大多数客户通常实施[Web SDK标记扩展](web-sdk-extension.md)，但您可以自行或在第三方标记管理系统中使用Web SDK JavaScript库。 请参阅GitHub上的[Alloy](https://github.com/adobe/alloy)以下载最新版本的库。

可以使用XDM的`identityMap`扩展身份数据以支持自定义ID和多个命名空间。 Adobe建议将Adobe Experience Cloud ID服务用作Analytics的主要标识符，并将其他身份管理选项用于高级方案。

如果您的组织使用Web SDK JavaScript库将数据发送到Adobe Analytics，则访客识别需要最少的配置。 访客ID服务以本机方式驻留在库中，仅要求您在&#x200B;**[!UICONTROL 命令中设置]** Edge域`configure`。 如果此字段设置为所需的值，则访客标识无需任何其他配置即可正常工作。
