---
description: 描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。
title: 添加 Data Warehouse 用户群组
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 添加 Data Warehouse 用户群组

描述管理员如何为用户群组启用 Data Warehouse 报表访问权限的步骤。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 用户管理]**。
1. 单击&#x200B;**[!UICONTROL 编辑群组]**。
1. 单击&#x200B;**[!UICONTROL 添加新用户群组]**。
1. 在&#x200B;**[!UICONTROL 定义用户群组]**&#x200B;部分的“群组名称”字段中，键入一个名称。请提供以下群组信息：

   例如：`Data Warehouse Access`。
1. 在&#x200B;**[!UICONTROL 群组描述]**&#x200B;字段中键入描述。
1. 在&#x200B;**[!UICONTROL 报表包访问]**&#x200B;部分，选择要让群组成员能够访问的报表包。
1. 在[!UICONTROL “工具”]下，启用&#x200B;**[!UICONTROL 所有工具]**。

   或者，单击&#x200B;**[!UICONTROL 自定义]**，然后启用&#x200B;**[!UICONTROL 自定义 Data Warehouse 报表]**。

1. 在[!UICONTROL “指定用户登录”]下，添加所需的用户登录。
1. 单击&#x200B;**[!UICONTROL 保存群组]**。

   添加到此群组的用户在下次登录时，将会看到 Data Warehouse 选项已添加到“[!UICONTROL Reports &amp; Analytics]”菜单中。

   >[!NOTE]
   >
   >如果发生权限冲突（例如，一个用户被分配到两个群组，其中一个群组拒绝对某个功能的访问，但另一个群组有权访问该功能），系统将会限制此权限。如果用户属于拒绝 Data Warehouse 访问的群组，则需要从这些群组中删除。

>[!MORELIKETHIS]
>
>* [群组 ](/help/admin/user-management2/c-user-groups/groups.md)

