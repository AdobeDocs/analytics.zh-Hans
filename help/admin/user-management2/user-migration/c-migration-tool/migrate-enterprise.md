---
description: 如何将 Analytics 用户帐户作为 Enterprise ID 或 Federated ID 迁移到 Admin Console。
title: 为 Enterprise ID 和 Federated ID 迁移 Analytics 用户帐户
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 为 Enterprise ID 和 Federated ID 迁移 Analytics 用户帐户{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

如何将 Analytics 用户帐户作为 Enterprise ID 或 Federated ID 迁移到 Admin Console。

## 先决条件 {#prereqs}

在 Admin Console 中管理用户的先决条件

对于新的域和目录，请按照以下步骤执行操作：

* 设置目录
* 设置域
* 将域链接到目录

有关帮助，请参阅[设置身份系统](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html)。

如果其他业务部门或团队已在另一个组织中创建了目录，请按照[目录信任](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html#Directorytrusting)中的步骤，在组织中建立要用于 Analytics 的目录。

## 为 Enterprise ID 和 Federated ID 迁移 用户帐户 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

在此过程中，您将执行以下操作：

* 从 **[!UICONTROL Analytics]** &gt; **[!UICONTROL Analytics 用户和资产]**&#x200B;下载用户登录列表。

* 从 **[!UICONTROL Admin Console]** &gt; **[!UICONTROL 用户]**&#x200B;下载当前用户列表。

* 比较列表（查找重复项，以避免覆盖 Admin Console 中的帐户数据）。
* 将包含 Enterprise ID 或 Federated ID 用户的已完成 [!DNL .csv]（从 **[!UICONTROL Admin Console]** &gt; **[!UICONTROL 用户]**）上载到 Admin Console。

如果需要将现有的 Adobe ID 用户帐户迁移到 Enterprise ID 或 Federated ID，请联系 Adobe 客户关怀并请求[批量切换用户身份](https://helpx.adobe.com/cn/enterprise/using/bulk-operations.html)。

**迁移用户帐户**

1. 使用以下方法之一（具体取决于您是否已迁移用户），从 Analytics 用户管理中下载 Analytics 用户登录文件 ([!DNL User Logins List.tab])。
   1. *在迁移之前，*&#x200B;导航至&#x200B;**[!UICONTROL 管理员]** &gt; **[!UICONTROL 用户管理（旧版）]**&gt; **[!UICONTROL 编辑用户]**，然后单击&#x200B;**[!UICONTROL 下载报表]**。

      ![](assets/download-report.png)

      只有未迁移用户的客户才会看到“下载报表”链接。

   1. *如果您已经迁移用户，*&#x200B;请导航至 **[!UICONTROL Analytics]** &gt; **[!UICONTROL Analytics 用户和资产]**。

      ![步骤信息](assets/admin-analytics-users-assets.png)

   1. 在 [!DNL Users] 页面中，选择“用户”，然后单击&#x200B;**[!UICONTROL 导出到 CSV]**。

      ![步骤信息](assets/export-csv-migrate.png)

   1. 在 Excel 中打开下载的 [!DNL User List.csv] 文件。

      准备将 *`Email`*、*`First Name`* 和 *`Last Name`* 的值复制到 [!DNL sample.csv] 文件中（在下一步中进行描述）。

      > [!IMPORTANT] CSV 文件中的值必须以逗号分隔。

      > [!TIP] 在此步骤中，Adobe 建议简化用户列表，以确保 Enterprise ID 或 Federated ID 迁移中只包含拥有有效电子邮件 ID 的用户。

1. 在 Admin Console 中，下载 Admin Console 用户列表：

   1. 导航至 [Admin Console](http://adminconsole.adobe.html/#) &gt; **[!UICONTROL 用户]**，然后单击[将用户列表导出到 CSV](https://helpx.adobe.com/cn/enterprise/using/users.html)。

      ![](assets/export-csv.png)

   1. 比较两个文件：对比已导出的 [!DNL .csv] 文件（本示例中为 [!DNL sample.csv]）中的现有 Admin Console 用户与 Analytics [!DNL User Logins List.csv] 文件中的用户。

      > [!IMPORTANT] 如果您发现了重复项，请将其从 Analytics [!DNL User Logins List.csv] 文件中删除。此步骤可帮助避免覆盖 Admin Console 中的现有 Experience Cloud 用户权限，并且可为您提供要迁移的帐户列表。

1. 从 Admin Console 中下载 CSV 模板：
   1. 在“用户”选项卡中，单击&#x200B;**[!UICONTROL 通过 CSV 添加用户]**，然后单击&#x200B;**[!UICONTROL 下载 CSV 模板]**。

      ![步骤信息](assets/add-users-csv.png)

   1. 选择&#x200B;**[!UICONTROL 标准模板]**。

      此步骤将下载 [!DNL sample.csv] 模板文件。

      ![](assets/download-csv-template.png)

1. 将 *`Email`*、*`First Name`* 和 *`Last Name`* 列值从 [!DNL User Logins List.tab] 复制到 [!DNL sample.csv] 模板中的相应列。

   **模板文件示例**

   ![](assets/sample.png)

1. 在模板 ([!DNL sample.csv]) 中，完成以下必填字段：

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>电子邮件 </p> </td> 
   <td colname="col2"> <p>从 <span class="filepath">User Logins List.tab</span> 复制。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名字 </p> </td> 
   <td colname="col2"> <p>从 <span class="filepath">User Logins List.tab</span> 复制。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>姓氏 </p> </td> 
   <td colname="col2"> <p>从 <span class="filepath">User Logins List.tab</span> 复制。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>身份类型 </p> </td> 
   <td colname="col2"> <p><span class="term">Federated ID</span> 或 <span class="term">Enterprise ID </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>域 </p> </td> 
   <td colname="col2"> <p>确保<span class="term">域</span>和<span class="term">电子邮件</span>列中的域与<a href="/help/admin/user-management2/user-migration/c-migration-tool/migrate-enterprise.md#prereqs"  >先决条件</a>中建立的域匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>国家/地区代码 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

有关 [!DNL .csv] 文件中字段的更多信息，请参阅 [CSV 文件格式](https://helpx.adobe.com/cn/enterprise/using/users.html)。

> [!NOTE] 其他列（例如 *`Product Configurations`* 和 *`Admin Roles`*）可以为空白。

1. 在 Admin Console 的“用户”选项卡中，单击&#x200B;**[!UICONTROL 通过 CSV 添加用户]**（如步骤 3 中所示）以上载模板文件。
1. 在 Analytics 中，运行迁移工具（如[迁移 Analytics 用户帐户](/help/admin/user-management2/user-migration/c-migration-tool/t-migrate-users.md)中所述）。
1. 单击&#x200B;**[!UICONTROL 迁移]** &gt; **[!UICONTROL 按照 Enterprise ID 进行迁移]**。

   ![步骤信息](assets/migrate-as-enterprise.png)

   单击&#x200B;**[!UICONTROL 迁移]**&#x200B;时，会将用户链接到 Admin Console 中的 Enterprise ID/Federated ID 帐户。Analytics 中旧版用户帐户的权限将与 **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL 产品配置文件]**&#x200B;中授予 Enterprise ID/Federated ID 登录的权限相匹配。用户 ID 将显示在“迁移已完成”分段中。您可以禁用其旧版 [!DNL my.omniture.com] 访问权限。

   在迁移用户后，“迁移状态”列下方的状态将从 *`Not Initiated`* 更改为 *`Migrated`*。

   迁移工具中显示的 Adobe ID 用户也可以在此过程中迁移。在执行身份切换之前，他们仍旧必须使用 Adobe ID 进行登录。请联系 Adobe 客户关怀，以帮助进行身份切换。
