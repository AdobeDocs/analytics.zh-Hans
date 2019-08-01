---
description: 了解如何禁用 Analytics 用户的旧版登录。
seo-description: 了解如何禁用 Analytics 用户的旧版登录。
seo-title: 禁用旧版登录
title: 禁用旧版登录
uuid: 085874b2-10bf-4a56-a337-f3104428 d71 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# 禁用旧版登录{#disable-legacy-logins}

了解如何禁用 Analytics 用户的旧版登录。

在您的用户从旧版 Analytics 用户管理系统迁移到 Adobe Admin Console 后，您可以禁用他们的旧版登录。如果用户尝试使用旧版登录，则禁用旧版登录会将其重定向到 Experience Cloud 登录。

1. Open the Migration tool in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. 选择要禁用其旧版登录的用户。

   ![](assets/user-info.png)

   The users that are eligible will have a status of *`Migrated`* under the Migration Status column. 在迁移用户之前将无法禁用其旧版登录。
1. Click **[!UICONTROL Disable Legacy Login]**, then click **[!UICONTROL Done]**.

   “禁用旧版登录”可指示哪些用户可以继续使用其旧版 [!DNL my.omniture.com] 用户名和密码。

   对于尚未迁移的用户，无法禁用其旧版登录。禁用后，用户必须使用其 Experience Cloud ID 登录和访问 Analytics。

