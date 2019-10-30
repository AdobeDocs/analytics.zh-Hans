---
description: Adobe Report Builder 现在具有类似于 Analytics 管理工具中的权限设置。
seo-description: Adobe Report Builder 现在具有类似于 Analytics 管理工具中的权限设置。
seo-title: 维度和量度的用户访问权限
solution: Analytics
title: 维度和量度的用户访问权限
topic: Report Builder
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 维度和量度的用户访问权限

Adobe Report Builder 现在具有类似于 Analytics 管理工具中的权限设置。

作为非管理员用户，您可能先前创建了一些工作簿，其请求指向您无权访问的维度和量度。现在可以强制执行这些权限。

例如，如果您刷新的请求包含您无权访问的维度或量度，则会出现“权限受限错误”：

![](assets/arb_restrc_perm.png)

对于您维护的&#x200B;**每个** Report Builder 工作簿，请按照以下说明操作：

1. 打开工作簿。
1. 刷新所有请求。
1. 如果系统提示您用户访问权限错误，请单击&#x200B;**[!UICONTROL 打开 CSV 文件]以获取权限受限错误的列表。**
1. 创建一个文件“AllRestrictedPermissionErrors.xlsx”，并将CSV文件中的受限权限错误列表复制／粘贴到此文件中。
1. 关闭 Report Builder 工作簿。

处理所有工作簿后，您应在“AllRestrictedPermissionErrors.xlsx”中拥有受限权限错误的完整列表。 将此列表发送给您的 Adobe Analytics 用户访问权限管理员，要求他授予您访问量度和维度的权限。
