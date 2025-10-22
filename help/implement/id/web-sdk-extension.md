---
title: 使用Web SDK标记扩展进行访客识别
description: 在实施Web SDK标记扩展时正确识别访客。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# 使用Web SDK标记扩展进行访客识别

Adobe Experience Platform数据收集中的Web SDK标记扩展使组织可以使用标记管理界面实施Web SDK。 通过扩展规则和操作，可轻松配置跨域ID共享和访客配置文件迁移等高级方案。 使用Web SDK可验证您的实施并支持无缝升级到Customer Journey Analytics。

可以使用XDM的`identityMap`扩展身份数据以支持自定义ID和多个命名空间。 Adobe建议将Adobe Experience Cloud ID服务用作Analytics的主要标识符，并将其他身份管理选项用于高级方案。

由于访客ID服务是以本机方式附加到标记扩展，因此它只需要将&#x200B;**[!UICONTROL Edge域]**&#x200B;设置为所需的值。 如果此字段设置正确，访客识别无需任何其他配置即可正常工作。

>[!NOTE]
>
>如果使用Web SDK标记扩展，则不要包含访客ID服务标记扩展。 只有在使用[Adobe Analytics扩展](analytics-extension.md)时，才需要访客ID服务标签扩展。
