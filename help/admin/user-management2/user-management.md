---
description: 在 Admin Console 中管理 Analytics 用户、群组和产品。
subtopic: Users and groups
title: 用户和产品管理
feature: Admin Tools
uuid: 891a8cb3-b77d-46f6-ab23-cbed49f215b5
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
source-git-commit: 1c066c0ebdf581c7a85b532534cf3088877fd046
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 44%

---

# 用户和产品管理

在 Admin Console 中管理 Analytics 用户、群组和产品。

>[!IMPORTANT]
>
>用户和产品管理已移至 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). Adobe 会通知您何时迁移用户。

## 面向 Admin Console 管理员的帮助资源 {#section_C13BBB89E4F248F193358BB3A59DD502}

| 任务或资源 | 描述 |
| --- | --- |
| 将Analytics用户ID迁移到Adobe Admin Console | Adobe 正协助 Analytics 管理员将用户 ID 迁移至 Adobe Admin Console。这项工作将分批进行。当轮到您迁移用户时，Adobe 将通过电子邮件告知 Analytics 管理员有关迁移的说明。迁移工具在 [Analytics用户管理](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html) 来简化这项任务。<p>**重要信息**:在您迁移用户的当天，您以前的权限组会自动复制到Admin Console。 您将无法在 Analytics 管理工具中邀请新用户或创建新群组。请查看将Analytics用户迁移到Adobe Admin Console中的常见问题解答和帮助，以了解有关如何准备迁移以及有关受影响的管理功能的信息。 |
| 启动Adobe Admin Console | 迁移用户帐户后，您可以在Admin Console中跨所有解决方案管理用户和产品。 导航到： `https://adminconsole.adobe.com/enterprise/`. 另请参阅 [管理Experience Cloud用户和产品](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html). |
| 管理Adobe Analytics产品配置文件、用户和权限 | 请参阅 [Adobe Admin Console中的Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=zh-Hans). |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->