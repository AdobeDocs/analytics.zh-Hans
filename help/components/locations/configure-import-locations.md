---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 配置云导入和导出位置
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: 9b263b0b2d41533630f225d4d4dcc9b1e0c4f1df
workflow-type: tm+mt
source-wordcount: '1687'
ht-degree: 31%

---

# 配置云导入和导出位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>创建和编辑位置时，请考虑以下事项：<ul><li>系统管理员可以限制用户创建位置，如[配置用户是否可以创建位置](/help/components/locations/locations-manager.md#configure-whether-users-can-create-locations)中所述。 如果无法按本节所述创建位置，请与系统管理员联系。</li><li>位置只能由创建该位置的用户或系统管理员编辑。</li></ul>

在您[配置云帐户](/help/components/locations/configure-import-accounts.md)后，您可以在该帐户上配置位置。 单个位置可用于以下任意目的（单个位置不能与多个目的相关联）：

* 使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)导出文件
* 使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)导出报告
* 使用[分类集](/help/components/classifications/sets/overview.md)导入架构

您必须为Adobe Analytics配置访问您的云帐户所需的信息。 此过程包括按照[配置Google导入和导出帐户](/help/components/locations/configure-import-accounts.md)中的说明添加和配置帐户(如Amazon S3角色ARN、Cloud Platform等)，然后添加和配置该帐户中的位置（如本文所述）。

有关如何查看和删除现有位置的信息，请参阅[位置管理器](/help/components/locations/locations-manager.md)。

## 开始创建或编辑位置

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **位置**]。

1. 在[!UICONTROL 位置]页面上，选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]选项以查看由您组织中的所有用户创建的位置。
   ![查看所有用户的位置](assets/locations-all-users.png)

1. 要添加新位置，请选择&#x200B;[!UICONTROL **添加位置**]。 （如果尚未添加帐户，请按照[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)中的说明添加帐户。）

   显示&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框

   或

   要编辑现有位置，请选择位置名称旁边的3点菜单，然后选择&#x200B;[!UICONTROL **编辑**]。

   显示&#x200B;[!UICONTROL **位置详细信息**]&#x200B;对话框。

1. 指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **名称**] | 位置的名称。 |
   | [!UICONTROL **描述**] | 提供帐户的简短描述，以帮助将它与同一帐户类型的其他帐户区分开来。 |
   | [!UICONTROL **与**]&#x200B;一起使用 | 选择您要将此位置与&#x200B;[!UICONTROL **数据馈送**]、[!UICONTROL **Data Warehouse**]&#x200B;还是&#x200B;[!UICONTROL **分类集**]&#x200B;一起使用。 <p>进行选择时，请考虑以下事项：</p><ul><li>单个位置不能用于多个目的。 例如，用于数据馈送的位置不能也用于“Data Warehouse”或“分类集”。</li><li>为避免某个位置出现文件冲突，请在使用该位置后不要更改&#x200B;[!UICONTROL **与**]&#x200B;一起使用字段的值。</li><li>如果要为电子邮件帐户创建位置，请在此字段中选择&#x200B;[!UICONTROL **Data Warehouse**]。 数据馈送和分类集不支持电子邮件位置。</li></ul> |
   | [!UICONTROL **使位置对组织中的所有用户都可用**] | 启用此选项可允许组织中的其他用户使用该位置。<p>共享位置时，请考虑以下事项：</p><ul><li>无法取消共享您共享的位置。</li><li>共享位置只能由位置的所有者编辑。</li><li>仅当与位置关联的帐户也共享时，才能共享位置。</li></ul> |
   | [!UICONTROL **位置帐户**] | 选择要创建此位置的位置帐户。 有关如何创建帐户的信息，请参阅[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)。 |

1. 要完成用于配置位置的表单，请继续下面的部分，该部分与您在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中选择的帐户类型相对应。 （此外，还提供其他旧版帐户类型，但不建议这样做。）

### Amazon S3 Role ARN

要配置Amazon S3角色ARN位置，请指定以下信息：

1. [开始创建或编辑位置](#begin-creating-or-editing-a-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储桶**] | 您要将 Adobe Analytics 数据发送到的 Amazon S3 账户中的存储段。 <p>确保Adobe提供的用户ARN具有`S3:PutObject`权限，以便将文件上载到此存储段。 </p><p>桶名称必须符合特定的命名规则。例如，它们的长度必须在 3 到 63 个字符之间，只能由小写字母、数字、点 (.) 和连字符 (-) 组成，并且必须以字母或数字开头和结尾。[若要了解完整的命名规则列表，请参阅 AWS 文档](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 若要导出数据，请使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)或[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。 若要导入数据，请使用[分类集](/help/components/classifications/sets/overview.md)。

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前使用[FTP将分类](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md)导入到Adobe Analytics，则需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Google Cloud Platform

若要配置 Google Cloud Platform 位置，请指定以下信息：

1. [开始创建或编辑位置](#begin-creating-or-editing-a-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储桶**] | GCP帐户中要将Adobe Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 |
   | [!UICONTROL **前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 若要导出数据，请使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)或[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。 若要导入数据，请使用[分类集](/help/components/classifications/sets/overview.md)。

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前使用[FTP将分类](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md)导入到Adobe Analytics，则需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Azure SAS

若要配置 Azure SAS 位置，请指定以下信息：

1. [开始创建或编辑位置](#begin-creating-or-editing-a-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器**] | 要将 Adobe Analytics 数据发送到的指定帐户中的容器。 |
   | [!UICONTROL **前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 若要导出数据，请使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)或[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。 若要导入数据，请使用[分类集](/help/components/classifications/sets/overview.md)。

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前使用[FTP将分类](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md)导入到Adobe Analytics，则需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Azure RBAC

若要配置 Azure RBAC 位置，请指定以下信息：

1. [开始创建或编辑位置](#begin-creating-or-editing-a-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **帐户**] | Azure存储帐户。 |
   | [!UICONTROL **容器**] | 要将 Adobe Analytics 数据发送到的指定帐户中的容器。确保授予将文件上传到您之前创建的 Azure 应用程序的权限。 |
   | [!UICONTROL **前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 若要导出数据，请使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)或[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。 若要导入数据，请使用[分类集](/help/components/classifications/sets/overview.md)。

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前使用[FTP将分类](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md)导入到Adobe Analytics，则需要上传FIN文件。 从云帐户导入时不需要此FIN文件。

### 电子邮件

要配置电子邮件位置，请指定以下信息：

1. [开始创建或编辑位置](#begin-creating-or-editing-a-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **主题**] | 电子邮件的主题。 |
   | [!UICONTROL **注释**] | 电子邮件的内容。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导出到使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)时配置的帐户和位置。 ([Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)或[分类集](/help/components/classifications/sets/overview.md)不支持电子邮件位置)。

### 旧帐户类型

这些旧帐户类型仅在使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)和[Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md)导出数据时可用。 在导入具有[分类集](/help/components/classifications/sets/manage/schema.md)的数据时，这些选项不可用。

+++FTP

数据馈送数据可以提交到Adobe或客户托管的FTP位置。 指定目录使用路径字段将馈送文件放置在文件夹中。

| 字段 | 功能 |
|---------|----------|
| [!UICONTROL **目录路径**] | 输入FTP服务器上目录的路径。 文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。 </br>例如，`/folder_name/folder_name`。 |

{style="table-layout:auto"}

+++

+++SFTP

数据馈送数据可以提交到Adobe或客户托管的SFTP位置。 目标站点必须包含有效的RSA或DSA公钥。 您可以在创建馈送时下载相应的公钥。

| 字段 | 功能 |
|---------|----------|
| [!UICONTROL **目录路径**] | 输入FTP服务器上目录的路径。 文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。 </br>例如，`/folder_name/folder_name`。 |

{style="table-layout:auto"}

+++

+++S3

您可以直接将数据仓库数据发送到 Amazon S3 存储段。此目标类型需要存储段名称、访问密钥 ID 和密钥。有关详细信息，请参阅 Amazon S3 文档中的 [Amazon S3 存储段命名要求](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)。

您为上传 Data Warehouse 数据提供的用户必须具有以下[权限](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

以下 16 个标准 AWS 区域（在必要时使用适当的签名算法）受支持：

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>不支持 cn-north-1 区域。

+++

+++Azure Blob

Data Warehouse 支持 Azure Blob 目标。需要容器、帐户和密钥。Amazon 会自动加密静态数据。当您下载数据时，数据会自动解密。有关详细信息，请参阅 Microsoft Azure 文档中的[创建存储帐户](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必须实施自己的流程来管理 Data Warehouse 目标上的磁盘空间。Adobe 不会从服务器中删除任何数据。

+++


