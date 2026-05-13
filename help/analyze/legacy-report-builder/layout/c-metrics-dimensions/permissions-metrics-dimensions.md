---
description: Adobe Report Builder 现在具有类似于 Analytics 管理工具中的权限设置。
title: 维度和量度的用户访问权限
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
TQID: https://experienceleague.adobe.com/p-nsvA1hqNBbwXesj5cumraamq2nEk1zVHgbby-XwEA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 40%

---

# 维度和量度的用户访问权限

{{legacy-arb}}

Adobe Report Builder具有类似于Analytics“管理工具”中的权限设置。

作为非管理员用户，您可能之前已创建包含指向您无权访问的维度和量度的请求的工作簿。 这些权限现已强制实施。

例如，如果刷新包含您无权访问的维度或量度的请求，您将收到“权限受限”错误。 该错误消息指出，由于管理权限，您的用户帐户无法使用某个请求。

![屏幕截图显示权限受限错误消息。](assets/arb_restrc_perm.png)

对于您维护的&#x200B;**每个**&#x200B;个Report Builder工作簿，请按照以下说明操作：

1. 打开工作簿。
1. 刷新所有请求。
1. 如果系统提示您出现“用户访问权限”错误，请单击&#x200B;**[!UICONTROL 打开CSV文件]**&#x200B;以获取权限受限错误列表的访问权限。
1. 创建文件“AllRestrictedPermissionErrors.xlsx”，然后将权限受限错误的列表从 CSV 文件复制/粘贴到此文件中。
1. 关闭 Report Builder 工作簿。

处理完所有工作簿后，“AllRestrictedPermissionErrors.xlsx”文件中应当具有权限受限错误的综合列表。 将此列表发送给您的 Adobe Analytics 用户访问权限管理员，要求他授予您访问量度和维度的权限。
