---
title: 使用Web SDK JavaScript库进行访客识别
description: 在实施Web SDK JavaScript库时正确识别访客。
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: 'https://experienceleague.adobe.com/k9u260HKJg6hhs7REAQ3-uE4pHvrUPBv6x8yLjZ5tvc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%
---
# 使用Web SDK JavaScript库进行访客识别

Adobe Experience Platform Web SDK JavaScript库(`alloy.js`)为所有Adobe CX Enterprise应用程序（包括Adobe Analytics）提供了统一的现代化数据收集方法。 虽然大多数客户通常实施[Web SDK标记扩展](web-sdk-extension.md)，但您可以自行或在第三方标记管理系统中使用Web SDK JavaScript库。 请参阅GitHub上的[Alloy](https://github.com/adobe/alloy)以下载最新版本的库。

可以使用XDM的[`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map)扩展身份数据以支持自定义ID和多个命名空间。 Adobe建议将ECID用作Analytics的主要标识符，并将其他身份管理选项用于高级方案。

如果您的组织使用Web SDK JavaScript库将数据发送到Adobe Analytics，则访客识别需要最少的配置。 Edge Network标识以本机方式植入到库，只需在`configure`命令中设置&#x200B;**[!UICONTROL Edge域]**&#x200B;即可。 如果此字段设置为所需的值，则访客标识无需任何其他配置即可正常工作。
