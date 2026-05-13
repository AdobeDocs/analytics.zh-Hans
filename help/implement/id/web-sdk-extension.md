---
title: 使用Web SDK标记扩展进行访客识别
description: 在实施Web SDK标记扩展时正确识别访客。
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: https://experienceleague.adobe.com/W42VkHT5yCW0yO-FbiAFHHKM8dF5NgCveZYGFOs7sYk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 0%

---

# 使用Web SDK标记扩展进行访客识别

Adobe Experience Platform数据收集中的Web SDK标记扩展使组织可以使用标记管理界面实施Web SDK。 通过扩展规则和操作，可轻松配置跨域ID共享和访客配置文件迁移等高级方案。 使用Web SDK可验证您的实施并支持无缝升级到Customer Journey Analytics。

可以使用XDM的`identityMap`扩展身份数据以支持自定义ID和多个命名空间。 Adobe建议将Adobe Experience Cloud ID服务用作Analytics的主要标识符，并将其他身份管理选项用于高级方案。

由于访客ID服务是以本机方式附加到标记扩展，因此它只需要将&#x200B;**[!UICONTROL Edge域]**&#x200B;设置为所需的值。 如果此字段设置正确，访客识别无需任何其他配置即可正常工作。

>[!NOTE]
>
>如果使用Web SDK标记扩展，则不要包含访客ID服务标记扩展。 只有在使用[Adobe Analytics扩展](analytics-extension.md)时，才需要访客ID服务标签扩展。
