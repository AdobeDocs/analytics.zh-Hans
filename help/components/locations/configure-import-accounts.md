---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 配置云导入和导出帐户
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: df9470f1870879ac91f00a021ed890bc6fb10cda
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 54%

---

# 配置云导入和导出帐户

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>创建和编辑帐户时，请考虑以下事项： <ul><li>系统管理员可以限制用户创建帐户，如[配置用户是否可以创建帐户](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts)中所述。 如果无法按本节所述创建帐户，请与系统管理员联系。</li><li>帐户只能由创建该帐户的用户或系统管理员编辑。</li></ul>

您可以配置用于以下任意或所有目的的云帐户：

* 使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)导出文件
* 使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)导出报告
* 使用[分类集](/help/components/classifications/sets/overview.md)导入架构

您需要为Adobe Analytics配置访问您的云帐户所需的信息。 此过程包括按照本文所述添加和配置帐户(如Amazon S3角色ARN、Google Cloud Platform等)，然后按照[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)中所述，添加和配置该帐户内的位置（如帐户内的文件夹）。

有关如何查看和删除现有帐户的信息，请参阅[位置管理器](/help/components/locations/locations-manager.md)。

要配置云导入或导出帐户，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **位置**]。
1. 在[!UICONTROL 位置]页面上，选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。
1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的帐户**]选项以查看由您组织中的所有用户创建的帐户。
   ![查看所有用户的帐户](assets/accounts-all-users.png)
1. 要创建新帐户，请选择&#x200B;[!UICONTROL **添加帐户**]。

   显示&#x200B;[!UICONTROL **位置帐户详细信息**]&#x200B;对话框。

   或

   要编辑现有帐户，请找到要编辑的帐户，然后选择&#x200B;[!UICONTROL **编辑详细信息**]&#x200B;按钮。

   显示&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框。

1. 指定以下信息：
|字段 | 函数 |
-------------------
| [!UICONTROL **位置帐户名称**] | 位置帐户的名称。 创建位置时将显示此名称 |
| [!UICONTROL **位置帐户描述**] | 提供帐户的简短描述，以帮助将其与同一帐户类型的其他帐户区分开来。 |
| [!UICONTROL **使帐户对贵组织的所有用户都可用**] | 启用此选项可允许组织中的其他用户使用该帐户。<p>共享帐户时，请考虑以下事项：</p><ul><li>无法取消共享您共享的帐户。</li><li>共享帐户只能由帐户的所有者编辑。</li><li>任何人都可以为共享帐户创建位置。</li></ul> |
| [!UICONTROL **帐户类型**] | 选择您的云帐户类型。 我们建议为每种帐户类型创建一个帐户，并根据需要在该帐户内设置多个位置。<p>系统管理员可以限制用户可以创建的帐户类型，如[配置用户是否可以创建帐户](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts)中所述。 如果无法按本节所述创建帐户，请与系统管理员联系。</p> |
1. 在&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定特定于所选帐户类型的信息。

   有关配置说明，请展开下面与您选择的&#x200B;[!UICONTROL **帐户类型**]&#x200B;对应的部分。 （此外，还提供其他旧版帐户类型，但不建议这样做。）

   **帐户类型**

   +++Amazon S3角色ARN

   若要配置 Amazon S3 角色 ARN 帐户，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必须提供角色 ARN（Amazon 资源名称），Adobe 可以使用它来获取对 Amazon S3 帐户的访问权限。为此，您需要为源帐户创建 IAM 权限策略，将该策略附加到用户，然后为目标帐户创建角色。有关特定信息，请参阅[此 AWS 文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/)。 |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   若要配置 Google Cloud Platform 帐户，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **项目 ID**] | 您的 Google Cloud 项目 ID。请参阅[有关获取项目 ID 的 Google Cloud 文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects)。 |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   若要配置 Azure SAS 帐户，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **密钥保管库 URI**] | <p>Azure 密钥保管库中 SAS 令牌的路径。要配置Azure SAS，必须使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参阅[有关如何分配密钥保管库访问策略的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal)。</p> |
   | [!UICONTROL **密钥保管库密码名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥保管库中，位于&#x200B;**密钥保管库**&#x200B;设置页面上。 有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。 |
   | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   若要配置 Azure RBAC 帐户，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |

   {style="table-layout:auto"}

+++

   +++Email

   >[!NOTE]
   >
   >电子邮件帐户只能用于[数据馈送](/help/export/analytics-data-feed/create-feed.md)。 ([Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)或[分类集](/help/components/classifications/sets/overview.md)不支持电子邮件帐户)。

   若要配置 Azure RBAC 帐户，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **收件人**] | 发送报表时，可以向特定用户发送电子邮件通知。指定单个电子邮件地址或电子邮件地址的逗号分隔列表。 |

   {style="table-layout:auto"}

+++

   **旧帐户类型**

   这些旧帐户类型仅在使用[数据馈送](/help/export/analytics-data-feed/create-feed.md)和[Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md)导出数据时可用。 在导入具有[分类集](/help/components/classifications/sets/manage/schema.md)的数据时，这些选项不可用。

   +++FTP

   数据馈送数据可以提交到Adobe或客户托管的FTP位置。 需要 FTP 主机、用户名和密码。可使用路径字段将馈送文件放置在文件夹中。文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **Host**] | 输入所需的FTP目标URL。 例如，`ftp://ftp.omniture.com`。 |
   | [!UICONTROL **路径**] | 可留空。 |
   | [!UICONTROL **用户名**] | 输入用户名以登录到FTP站点。 |
   | [!UICONTROL **密码并确认密码**] | 输入登录FTP站点的密码。 |

   {style="table-layout:auto"}

+++

   +++SFTP

   提供了对数据馈送的 SFTP 支持。需要 SFTP 主机、用户名，以及包含有效 RSA 或 DSA 公钥的目标站点。您可以在创建馈送时下载相应的公钥。

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

   Data Warehouse支持Azure Blob目标。 需要容器、帐户和密钥。Amazon 会自动加密静态数据。当您下载数据时，数据会自动解密。有关详细信息，请参阅 Microsoft Azure 文档中的[创建存储帐户](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

   >[!NOTE]
   >
   >您必须实施自己的流程来管理 Data Warehouse 目标上的磁盘空间。Adobe 不会从服务器中删除任何数据。

+++

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 继续[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)。
