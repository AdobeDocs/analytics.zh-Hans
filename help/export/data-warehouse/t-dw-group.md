---
description: 描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。
title: 添加 Data Warehouse 用户群组
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 添加 Data Warehouse 用户群组

描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. 单击 **[!UICONTROL Edit Groups]**.
1. 单击 **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 请提供以下群组信息：

   例如：`Data Warehouse Access`。
1. 在字段中键入说 **[!UICONTROL Group Description]** 明。
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. 在下 [!UICONTROL Tools]面，启用 **[!UICONTROL All Tools]**。

   或者，单击， **[!UICONTROL Customize]**&#x200B;然后启用 **[!UICONTROL Custom Data Warehouse Report]**。

1. 在下 [!UICONTROL Assign User Logins]面，添加所需的用户登录名。
1. 单击 **[!UICONTROL Save Group]**.

   添加到此群组的用户在下次登录时，将会看到 Data Warehouse 选项已添加到“[!UICONTROL Reports & Analytics]”菜单中。

   >[!NOTE]
   >
   >如果发生权限冲突（例如，一个用户被分配到两个群组，其中一个群组拒绝对某个功能的访问，但另一个群组有权访问该功能），系统将会限制此权限。如果用户属于拒绝 Data Warehouse 访问的群组，则需要从这些群组中删除。

>[!MORELIKETHIS]
>
>* [群组 ](/help/admin/user-management2/c-user-groups/groups.md)

