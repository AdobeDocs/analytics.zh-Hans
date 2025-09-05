---
description: 将用户从旧版 Analytics 用户管理系统迁移到 Admin Console。
title: 为 Adobe ID 迁移 Analytics 用户帐户
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 99%

---

# 迁移 Analytics 用户帐户以使用 Adobe ID

将用户从旧版 Analytics 用户管理系统迁移到 Admin Console。

>[!NOTE]
>
>如果未通过 Experience Cloud 登录的管理员尝试访问用户 ID 迁移工具，则将其重定向到 Experience Cloud 登录页面。

1. 导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 用户 ID 迁移]**。

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   “用户 ID 迁移”页面包含两个部分：“迁移进度”**&#x200B;和“用户信息”**。

## 迁移进度

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 阶段 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>迁移已完成 </p> </td> 
      <td colname="col2"> <p>用户已接受邀请。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>旧版登录已禁用 </p> </td> 
      <td colname="col2"> <p>使用公司 ID 的旧版登录被禁用。用户将立即使用其 Adobe ID 或 Enterprise ID 访问 Experience Cloud。当所有用户都达到此阶段时，即表明您完成了迁移。 </p> <p>在迁移中，旧版登录将被禁用。用户将被重定向到 <span class="filepath">experiencecloud.adobe.com</span>，并且必须使用 Adobe ID 或 Enterprise ID 登录。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

## 用户信息

“用户信息”概述了组织中的用户，并按域名分隔。

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
<thead> 
<tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
</tr>
</thead>
<tbody> 
<tr> 
   <td colname="col1"> <p>域 </p> </td> 
   <td colname="col2"> <p>域特定于当前 Analytics 用户群的电子邮件 ID。域只能由一个组织的声明，并且只有系统管理员才能声明域。有关更多信息，请参阅<a href="https://helpx.adobe.com/cn/enterprise/help/request-access-to-claimed-domain.html">请求对声明域的访问权限</a>。 </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>声明的域 </p> </td> 
   <td colname="col2"> <p>如果要按 Enterprise ID 或 Federated ID 迁移用户，您必须是系统管理员，并通过 Adobe Admin Console 声明可用域，然后才能迁移用户。在<a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">这里</a>了解更多。 </p> <p>如果不想为 Enterprise ID 或 Federated ID 声明任何域，请跳过此步骤，并继续按 Adobe ID 迁移用户。在<a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">这里</a>了解有关 ID 类型的更多信息。 </p> </td> 
</tr> 
</tbody> 
</table>

1. 找到包含待迁移用户 ID 的域，然后在&#x200B;**[!UICONTROL 要求迁移]**&#x200B;下单击&#x200B;**[!UICONTROL 选择用户]**。
1. 在 [!DNL Users] 页面上，选择要迁移的用户，然后单击&#x200B;**[!UICONTROL 迁移]**。

   在单击&#x200B;**[!UICONTROL 迁移]**&#x200B;后，用户将收到一封邀请函（迁移已启动）并且必须接受它。此操作会将用户 ID 移至“迁移已完成”。然后，您可以关闭他们对 `[!DNL my.omniture.com].` 的旧版访问权限

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. 指定要迁移用户的 ID 类型（Adobe ID 或 Enterprise ID）

   在迁移用户后，“迁移状态”列下方的状态将从 *`Not Initiated`* 更改为 *`Migrated`*。

   如果显示 *`Failed`*，请将光标悬停在图标上方，以查看有关迁移失败原因的描述。
