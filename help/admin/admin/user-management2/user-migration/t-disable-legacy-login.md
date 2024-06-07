---
description: 了解如何禁用 Analytics 用户的旧版登录。
title: 禁用旧版登录
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# 禁用旧版登录

了解如何禁用 Analytics 用户的旧版登录。

在您的用户从旧版 Analytics 用户管理系统迁移到 Adobe Admin Console 后，您可以禁用他们的旧版登录。如果用户尝试使用旧版登录，则禁用旧版登录会将其重定向到 Experience Cloud 登录。

1. 在 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 用户 ID 迁移]**&#x200B;中打开迁移工具。
1. 在 [!DNL User Information] 部分中，找到包含待处理用户的域，然后单击&#x200B;**[!UICONTROL 选择用户]**。
1. 选择要禁用其旧版登录的用户。

   ![](/help/admin/admin/user-management2/user-migration/assets/user-info.png)

   符合条件的用户在“迁移状态”列下的状态为 *`Migrated`*。在迁移用户之前将无法禁用其旧版登录。
1. 单击&#x200B;**[!UICONTROL 禁用旧版登录]**，然后单击&#x200B;**[!UICONTROL 完成]**。

   “禁用旧版登录”可指示哪些用户可以继续使用其旧版 [!DNL my.omniture.com] 用户名和密码。

   对于尚未迁移的用户，无法禁用其旧版登录。禁用后，用户必须使用其 Experience Cloud ID 登录和访问 Analytics。
