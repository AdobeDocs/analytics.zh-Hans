---
description: 描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。
seo-description: 描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。
seo-title: 添加 Data Warehouse 用户群组
solution: Analytics
title: 添加 Data Warehouse 用户群组
topic: Data Warehouse
uuid: d89294db-caa3-4044-b70 d-65b012 b0 c1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 添加 Data Warehouse 用户群组

描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 请提供以下群组信息：

   例如：`Data Warehouse Access`。
1. Type a description in the **[!UICONTROL Group Description]** field.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. Under [!UICONTROL Tools], enable **[!UICONTROL All Tools]**.

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. 在[!UICONTROL “指定用户登录”]下，添加所需的用户登录。
1. Click **[!UICONTROL Save Group]**.

   添加到此群组的用户在下次登录时，将会看到 Data Warehouse 选项已添加到“[!UICONTROL Reports &amp; Analytics]”菜单中。

   >[!NOTE]
   >
   >如果存在冲突权限(如分配给两个用户组的用户，其中一个用户组拒绝访问某个功能，而另一个用户组授予该访问权限)，则系统会限制权限。如果用户属于拒绝 Data Warehouse 访问的群组，则需要从这些群组中删除。

>[!MORE_LIKE_THIS]
>
>* [群组 ](/help/admin/user-management2/c-user-groups/groups.md)

