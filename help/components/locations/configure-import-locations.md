---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 配置云导入和导出位置
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: 9b36cfef9fbc3f6ce4e1fc1485a3eb8c2240a96c
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 31%

---

# 配置云导入和导出位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

您可以配置云帐户（以及在该帐户上的位置）。 单个位置可用于以下任意目的(单个位置不能与多个目的相关联，例如数据馈送和Data Warehouse，或Data Warehouse和分类集)：

* 导出文件，使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md)
* 导出报告，使用 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* 使用以下方式导入架构 [分类集](/help/components/classifications/sets/overview.md)

您必须为Adobe Analytics配置访问您的云帐户所需的信息。 此过程包括添加和配置帐户(如Amazon S3角色ARN、Google Cloud Platform等)，如中所述 [配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)，然后在该帐户中添加和配置位置（如本文所述）。

## 开始创建或编辑云导出位置

1. 在Adobe Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **位置**].
1. 在 [!UICONTROL 位置] 页面上，选择 [!UICONTROL **位置**] 选项卡。
1. 要创建新位置，请选择 [!UICONTROL **添加位置**]. (如果尚未添加帐户，请按照中的说明添加一个帐户 [配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md).)

   或

   要编辑现有位置，请选择 [!UICONTROL **位置名称**] 要编辑的位置对应的列，然后选择 [!UICONTROL **编辑**].
此时将显示“位置”对话框。

1. 指定以下信息： |字段 | 函数 | ------------------- | [!UICONTROL **名称**] | 位置的名称。  |
| [!UICONTROL **描述**] | 提供帐户的简短描述，以帮助将它与同一帐户类型的其他帐户区分开来。| | [!UICONTROL **使用和**] | 选择是否要将此位置与 [!UICONTROL **数据馈送**]， [!UICONTROL **Data Warehouse**]，或 [!UICONTROL **分类集**]. <p>进行选择时，请考虑以下事项：</p><ul><li>单个位置不能用于多个目的。 例如，用于数据馈送的位置不能也用于“Data Warehouse”或“分类集”。</li><li>为避免某个位置出现文件冲突，请勿更改 [!UICONTROL **使用和**] 位置后的字段。</li></ul> | | [!UICONTROL **位置帐户**] | 选择要创建此位置的位置帐户。 有关如何创建帐户的信息，请参阅 [添加帐户](#add-an-account). |

1. 在&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定特定于位置帐户的帐户类型的信息。

   继续下面的部分，该部分与您在 [!UICONTROL **位置帐户**] 字段。 （此外，还提供其他旧版帐户类型，但不建议这样做。）



### Amazon S3 Role ARN

要配置Amazon S3角色ARN位置，请指定以下信息：

1. [开始创建或编辑云导出位置](#begin-creating-or-editing-a-cloud-export-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储段名称**] | 您要将 Adobe Analytics 数据发送到的 Amazon S3 账户中的存储段。 <p>确保Adobe提供的用户ARN具有 `S3:PutObject` 权限以将文件上传到此存储段。 </p><p>存储段名称必须满足特定的命名规则。 例如，其长度必须介于3到63个字符之间，只能由小写字母、数字、点(.)和连字符(-)组成，并且必须以字母或数字开头和结尾。 [AWS文档中提供了命名规则的完整列表](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html). </p> |
   | [!UICONTROL **密钥前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 要导出数据，请使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md) 或 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). 要导入数据，请使用 [分类集](/help/components/classifications/sets/overview.md).

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前已使用 [用于导入分类的FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 到Adobe Analytics，您需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Google Cloud Platform

要配置Google Cloud Platform位置，请指定以下信息：

1. [开始创建或编辑云导出位置](#begin-creating-or-editing-a-cloud-export-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储段名称**] | GCP帐户中要将Adobe Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 |
   | [!UICONTROL **密钥前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 要导出数据，请使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md) 或 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). 要导入数据，请使用 [分类集](/help/components/classifications/sets/overview.md).

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前已使用 [用于导入分类的FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 到Adobe Analytics，您需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Azure SAS

要配置Azure SAS位置，请指定以下信息：

1. [开始创建或编辑云导出位置](#begin-creating-or-editing-a-cloud-export-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名称**] | 要将 Adobe Analytics 数据发送到的指定帐户中的容器。 |
   | [!UICONTROL **密钥前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 要导出数据，请使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md) 或 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). 要导入数据，请使用 [分类集](/help/components/classifications/sets/overview.md).

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前已使用 [用于导入分类的FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 到Adobe Analytics，您需要上传FIN文件。 从云帐户导入时不需要此FIN文件。


### Azure RBAC

要配置Azure RBAC位置，请指定以下信息：

1. [开始创建或编辑云导出位置](#begin-creating-or-editing-a-cloud-export-location)，如上所述。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名称**] | 要将 Adobe Analytics 数据发送到的指定帐户中的容器。确保授予将文件上传到您之前创建的 Azure 应用程序的权限。 |
   | [!UICONTROL **密钥前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。例如，`folder_name/` |
   | [!UICONTROL **帐户名称**] | Azure存储帐户。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   您现在可以将数据导入或导出到您配置的帐户和位置，或从配置的帐户和位置导出数据。 要导出数据，请使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md) 或 [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). 要导入数据，请使用 [分类集](/help/components/classifications/sets/overview.md).

   导入数据后，不会从云目标中删除导入的数据。

   >[!NOTE]
   >
   >   如果您之前已使用 [用于导入分类的FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 到Adobe Analytics，您需要上传FIN文件。 从云帐户导入时不需要此FIN文件。

### 旧帐户类型

这些旧帐户类型仅在导出数据时使用 [数据馈送](/help/export/analytics-data-feed/create-feed.md) 和 [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). 在使用导入数据时，这些选项不可用 [分类集](/help/components/classifications/sets/manage/schema.md).

+++FTP

数据馈送数据可以提交到Adobe或客户托管的FTP位置。 指定目录使用路径字段将馈送文件放置在文件夹中。

| 字段 | 功能 |
|---------|----------|
| [!UICONTROL **目录路径**] | 输入FTP服务器上目录的路径。 文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。 </br>例如， `/folder_name/folder_name`. |

{style="table-layout:auto"}

+++

+++SFTP

数据馈送数据可以提交到Adobe或客户托管的SFTP位置。 目标站点必须包含有效的RSA或DSA公钥。 您可以在创建馈送时下载相应的公钥。

| 字段 | 功能 |
|---------|----------|
| [!UICONTROL **目录路径**] | 输入FTP服务器上目录的路径。 文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。 </br>例如， `/folder_name/folder_name`. |

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


