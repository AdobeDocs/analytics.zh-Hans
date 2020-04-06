---
description: 描述如何通过 FTP 上载数据文件的步骤。
subtopic: Classifications
title: FTP 导入
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# FTP 导入

描述如何通过 FTP 上载数据文件的步骤。

## FTP 导入 {#concept_2F965BE873254546A61FB755F25299FD}

描述如何通过 FTP 上载数据文件的步骤。

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

以下建议的限制很重要：

* 与几个大文件相比，大量小文件会导致处理速度降低。 这是由于需要为较小的作业排队和排定优先级。
* 请将大文件分为50 MB的块。 这不是必需的，但建议这样做，因为这样可以更好地了解后端的进度。 此外，如果我们处理您的作业时出错，作业将重新启动；大文件会导致在此方案中重做大量工作。

初始设置使用大量原始数据填充分类数据库，或重新构建分类，而不是对几行重新分类或添加行。

在报表包中进行初始上传（对于给定的变量或报表）后，Adobe建议在后续导入中仅上传新行和更新行。 未更改的行应从将来的上载中忽略。

您上传的每个新键值都将计入该月变量的唯一值。

如果超过当月的唯一值，您将看不到报告中超出的唯一值的相应分类数据。 您可以在数据仓库或临时分析中查看这些分类。

>[!NOTE] 处理分类数据文件所需的时间因文件大小和 Adobe 服务器已在处理的当前文件数而异。处理数据文件通常不超过72小时。

在通过 FTP 上载数据之前，请先创建 FTP 帐户。有关详细信息，请参阅[创建 FTP 帐户](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

## 通过 FTP 导入分类 {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

描述如何使用FTP帐户将分类导入Adobe Analytics的步骤。

有关创建FTP帐户的详细信息，请参 [阅创建FTP帐户](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. 单击 **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. 单 **[!UICONTROL Import File]**&#x200B;击，然后单击 **[!UICONTROL FTP Import]**。
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. 使用 FTP 访问信息（主机、登录名、密码），通过您选择的 FTP 客户端访问 FTP 服务器。
1. 将数据文件（[!DNL .tab] 或 [!DNL .txt]）上载到 FTP 服务器。
1. 上载数据文件之后，再上载指示可以处理文件的 FIN 文件。

   FIN 文件是一个与您的数据文件同名的空文件，扩展名为 [!DNL .fin]。例如，如果您的数据文件为 [!DNL classdata1.tab]，则 文件名为 [!DNL classdata1.fin].fin。

Adobe会定期检索已上载的数据文件，其中有关联的FIN文件。 Adobe会将其导入到FTP帐户配置中指定的报表包和数据集中。

## 创建 FTP 帐户 {#task_C019268E6C934C7C95F4326F42A22CCF}

在通过 FTP 上载数据之前，请先创建 FTP 帐户。>

<!-- 

t_create_an_ftp_account.xml

 -->

有关 Adobe FTP 服务器的其他详细信息，请参阅 [FTP 和 sFTP](https://marketing.adobe.com/resources/help/zh_CN/whitepapers/ftp/)。

1. 单击 **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. 单 **[!UICONTROL Import File]**&#x200B;击，然后单击 **[!UICONTROL FTP Import]**。
1. 在选项卡 **[!UICONTROL Import File]** 上，单击 **[!UICONTROL Add New]**。
1. 指定 FTP 帐户详细信息：

   | 元素 | 描述 |
   |---|---|
   | 名称 | FTP帐户名称。 |
   | 要分类的数据集 | 从下拉列表中，选择要分类的数据集（营销报告变量）。 |
   | 选择报表包 | 选择要对选定数据集进行分类的报表包。 要选择多个报表包，每个选定报表包的分类必须相同。 |
   | 覆盖冲突数据 | 选择此选项可覆盖重复数据。 如果要更新现有分类，则此选项很有用。 如果要添加其他分类，则不建议使用此选项。 |
   | 完成导入后 | 选择此选项后，将更新后的数据集自动导出到同一FTP帐户，一旦导入完成，指定接收此FTP帐户通知的电子邮件地址。 |
   | 通知收件人 | 指定接收此FTP帐户通知的电子邮件地址。 |
   | 授权 | （必需）授权Adobe自动导入发送到新FTP帐户的所有数据文件。 |

1. 单击 **[!UICONTROL Save]**.

创建之后，您可以通过单击所需的 FTP 帐户旁边的相应链接来编辑或删除 FTP 帐户。
