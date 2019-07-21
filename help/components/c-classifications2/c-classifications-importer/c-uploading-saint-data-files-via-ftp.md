---
description: 描述如何通过 FTP 上载数据文件的步骤。
seo-description: 描述如何通过 FTP 上载数据文件的步骤。
seo-title: FTP导入
solution: Analytics
subtopic: 分类
title: FTP导入
topic: 管理工具
uuid: a914970d-ba02-4111-9dcf-06448f71 b9 f3 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# FTP导入

描述如何通过 FTP 上载数据文件的步骤。

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

描述如何通过 FTP 上载数据文件的步骤。

**[!UICONTROL 管理员]** &gt; **[!UICONTROL 分类导入程序]**。

以下建议的限制很重要：

* 小文件过多会造成比少量大文件更慢的处理速度。这是因为这些小作业需要大量的排队和优先级安排操作。
* 请将大文件分为多个 50 MB 的数据块。这不是必需的，但建议这么做，因为这样可以更好地了解后端进程。另外，如果我们在处理您的作业时出现错误，则将会重新开始处理作业；而大文件则会在这种情况下导致重做大量工作。

初始设置使用大量原始数据填充分类数据库，或重新构建分类，而不是对某些行重新分类或添加行。

在报表包中进行初始上载（针对给定的变量或报表）之后，Adobe 建议在后续导入中只上载新行和更新的行。将来上载时应忽略未更改的行。

您上载的每个新键值都会计入当月该变量的独立值。

如果您超出了当月的独立值，将无法在报表中看到超出独立值所对应的分类数据。您可以在 Data Warehouse 或 Ad Hoc Analysis 中查看这些分类。

>[!NOTE]
>
>处理分类数据文件所需的时间因文件大小和Adobe服务器已处理的当前文件数而异。处理数据文件的时间通常不超过 72 小时。

在通过 FTP 上载数据之前，请先创建 FTP 帐户。有关详细信息，请参阅[创建 FTP 帐户](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

## 通过 FTP 导入分类 {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

描述如何使用 FTP 帐户将分类导入 Adobe Analytics 的步骤。

有关创建 FTP 帐户的更多信息，请参阅[创建 FTP 帐户](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. 使用 FTP 访问信息（主机、登录名、密码），通过您选择的 FTP 客户端访问 FTP 服务器。
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1. 上载数据文件之后，再上载指示可以处理文件的 FIN 文件。

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

Adobe 会定期检索已上载的具有关联 FIN 文件的数据文件。然后，Adobe 会将其导入 FTP 帐户配置中指定的报表包和数据集中。

## 创建 FTP 帐户 {#task_C019268E6C934C7C95F4326F42A22CCF}

在通过 FTP 上载数据之前，请先创建 FTP 帐户。&gt;

<!-- 

t_create_an_ftp_account.xml

 -->

有关 Adobe FTP 服务器的其他详细信息，请参阅 [FTP 和 sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/)。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
1. 指定 FTP 帐户详细信息：

   | 元素 | 描述 |
   |---|---|
   | 名称 | FTP 帐户名称。 |
   | 要分类的数据集 | 从下拉列表中，选择要进行分类的数据集（市场营销报告变量）。 |
   | 选择报表包 | 选择要将所选数据集进行分类的报表包。要选择多个报表包，每个所选报表包的分类必须完全相同。 |
   | 覆盖冲突的数据 | 选择此选项可覆盖重复数据。如果您要更新现有的分类，则此选项非常有用。如果您要添加其他分类，则建议不要使用此选项。 |
   | 导入完成后 | 选择此选项，可在导入完成后，在指定了接收此 FTP 帐户相关通知的电子邮件地址的情况下，自动将更新的数据集导出到同一 FTP 帐户。 |
   | 通知收件人 | 指定电子邮件地址来接收有关此 FTP 帐户的通知。 |
   | 授权 | （必需）授权 Adobe 自动导入发送到新 FTP 帐户的所有数据文件。 |

1. 单击&#x200B;**[!UICONTROL 保存]**。

创建之后，您可以通过单击所需的 FTP 帐户旁边的相应链接来编辑或删除 FTP 帐户。
