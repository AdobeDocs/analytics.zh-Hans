---
description: 描述如何创建 Data Warehouse 请求的步骤。
title: 为 Data Warehouse 请求配置报表目标
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d78a2d683073d90b0b92db50253b3755ff909d9e
workflow-type: tm+mt
source-wordcount: '1980'
ht-degree: 82%

---

# 为 Data Warehouse 请求配置报表目标

提供了在创建 Data Warehouse 请求时可使用的多种配置选项。以下信息描述如何为请求配置报表目标。

有关如何开始创建请求的信息以及其他重要配置选项的链接，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

>[!NOTE]
>
>在配置报表目标时，请考虑以下事项：
>
>* 我们建议您使用云帐户或电子邮件作为报表目标。虽然[旧版 FTP 和 SFTP 帐户](#legacy-destinations)可用，但建议不要使用这些帐户。
>
>* 您之前配置的任何云帐户都可以用于 Data Warehouse。您可以通过以下任一方式配置云帐户：
>
>   * 配置[数据馈送](/help/export/analytics-data-feed/create-feed.md)时
>   
>   *  [导入 Adobe Analytics 分类数据时](/help/components/locations/locations-manager.md)（可以使用帐户，但不能使用在这些帐户上配置的任何位置。）
>   
>   * 从位置管理器中，在[组件 > 位置](/help/components/locations/configure-import-accounts.md)内。
>
>* 云帐户与您的 Adobe Analytics 用户帐户关联。其他用户无法使用或查看您配置的云帐户。
>
>* 您可以在[组件 > 位置](/help/components/locations/configure-import-accounts.md)中的位置管理器中编辑您创建的任何位置

要配置将 Data Warehouse 报表发送到的目标，请执行以下操作：

1. 如果还没有，请选择“**[!UICONTROL 工具]**”>“**[!UICONTROL Data Warehouse]**”>“[!UICONTROL **添加**]”，开始在 Adobe Analytics 中创建请求。

   有关更多详细信息，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

1. 在新的 Data Warehouse 请求页面上，选择&#x200B;[!UICONTROL **报表目标**]&#x200B;选项卡。

   ![“报表目标”选项卡](assets/dw-report-destination.png)

1. （视情况而定）如果已在 Adobe Analytics 中配置云帐户（以及该帐户上的一个目标），您可以将其用作报告目标：

   >[!NOTE]
   >
   >仅当您配置了帐户或与您所属的组织共享帐户时，您才可以使用帐户。
   >
   >如果您是系统管理员，则&#x200B;[!UICONTROL **显示所有目标**]&#x200B;选项可用。如果要访问已由组织中的任意用户创建的所有帐户和位置，请启用此选项。

   1. 从&#x200B;[!UICONTROL **帐户**]&#x200B;下拉菜单中选择帐户。

      您在 Adobe Analytics 的以下任何区域中配置的任何云帐户均可供使用：

      * 导入 Adobe Analytics 分类数据时，如[架构](/help/components/classifications/sets/manage/schema.md)中所述。

        不过，不能使用配置用于导入分类数据的任何位置。相反，请按如下所述添加新目标。

      * 在“位置”区域配置帐户和位置时，如[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)和[配置云导入和导出位置](/help/components/locations/configure-import-locations.md)中所述。

   1. 从&#x200B;[!UICONTROL **选择目标**]&#x200B;下拉菜单中选择与帐户关联的目标。<!-- Is this correct? -->

1. （视情况而定）如果您无权访问已在 Adobe Analytics 中配置的云帐户，则可以配置一个：

   1. 选择&#x200B;[!UICONTROL **帐户**]&#x200B;下拉菜单，然后选择&#x200B;[!UICONTROL **添加帐户**]。

   1. 在添加帐户对话框中，指定以下信息：

      | 字段 | 功能 |
      |---------|----------|
      | [!UICONTROL **位置帐户名称**] | 位置帐户的名称。 此名称会在创建位置时出现 |
      | [!UICONTROL **位置帐户描述**] | 提供帐户的简短描述，以帮助将它与同一帐户类型的其他帐户区分开来。 |
      | [!UICONTROL **使帐户对贵组织的所有用户都可用**] | 启用此选项可允许组织中的其他用户使用该帐户。<p>共享帐户时，请考虑以下事项：</p><ul><li>无法取消共享您共享的帐户。</li><li>共享帐户只能由帐户的所有者编辑。</li><li>任何人都可以为共享帐户创建位置。</li></ul> |
      | [!UICONTROL **帐户类型**] | 选择您的云帐户类型。我们建议为每种帐户类型创建一个帐户，并根据需要在该帐户内设置多个位置。<p>系统管理员可以限制用户可以创建的帐户类型，如[配置用户是否可以创建帐户](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts)中所述。 如果无法按本节所述创建帐户，请与系统管理员联系。</p> |

   1. 在&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定特定于所选帐户类型的信息。

      有关配置说明，请展开下面与您选择的&#x200B;[!UICONTROL **帐户类型**]&#x200B;对应的部分。 （此外，还提供其他旧版帐户类型，但不建议这样做。）

      **帐户类型**

      +++Amazon S3 Role ARN

      **注意：**&#x200B;在将Amazon S3与Data Warehouse结合使用时，仅支持SSE-S3加密。

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
      | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
      | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
      | [!UICONTROL **密钥保管库 URI**] | <p>Azure 密钥保管库中 SAS 令牌的路径。要配置Azure SAS，必须使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参阅[有关如何分配密钥保管库访问策略的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal)。</p><p>或</p><p>如果要直接授予访问角色而不创建访问策略，请参阅[Microsoft Azure文档，了解如何使用Azure门户分配Azure角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal)。 这会添加应用程序ID的角色分配，以访问密钥保管库URI。 </p> |
      | [!UICONTROL **密钥保管库密码名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥保管库中，位于&#x200B;**密钥保管库**&#x200B;设置页面上。 有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。 |
      | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |

      {style="table-layout:auto"}

      +++   

      +++Azure RBAC

      若要配置 Azure RBAC 帐户，请指定以下信息：

      | 字段 | 功能 |
      |---------|----------|
      | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
      | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
      | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |

      {style="table-layout:auto"}

      +++

      +++电子邮件

      >[!NOTE]
      >
      >电子邮件帐户只能用于[数据馈送](/help/export/analytics-data-feed/create-feed.md)。 (不支持电子邮件帐户使用[Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)或[分类集](/help/components/classifications/sets/overview.md))。

      若要配置 Azure RBAC 帐户，请指定以下信息：

      | 字段 | 功能 |
      |---------|----------|
      | [!UICONTROL **收件人**] | 发送报表时，可以向特定用户发送电子邮件通知。指定单个电子邮件地址或电子邮件地址的逗号分隔列表。 |

      {style="table-layout:auto"}

      +++

1. 继续在&#x200B;[!UICONTROL **报表选项**]&#x200B;选项卡上配置您的 Data Warehouse 请求。有关更多信息，请参阅[配置 Data Warehouse 请求的报表选项](/help/export/data-warehouse/create-request/dw-request-report-options.md)。

## 旧帐户类型

>[!IMPORTANT]
>
>此部分中描述的目标是旧目标，建议不要使用这些目标。相反，在创建 Data Warehouse 目标时，请使用以下目标之一：Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS 或 Email。有关建议的这些目标的详细信息，请参阅上面的信息。

以下信息提供了每个旧目标的配置信息：

### FTP

Data Warehouse 数据可以提交到由 Adobe 或客户托管的 FTP 位置。需要 FTP 主机、用户名和密码。可使用路径字段将馈送文件放置在文件夹中。文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。

填写可用字段时，请使用以下信息：

#### 帐户字段

* [!UICONTROL **帐户名称**]：FTP 帐户的名称。

* [!UICONTROL **帐户描述**]：FTP 帐户的描述。

* [!UICONTROL **主机名**]：输入所需的 FTP 目标 URL。例如，`ftp.company.com`。

  >[!NOTE]
  >
  >  不要在 URL 的开头包括 `ftp://`。

* [!UICONTROL **用户名**]：输入用于登录 FTP 网站的用户名。

* [!UICONTROL **密码和确认密码**]：输入用于登录 FTP 网站的密码。

#### 位置字段

* [!UICONTROL **位置名称**]：要将文件发送到的 FTP 帐户中位置的名称。

* [!UICONTROL **位置描述**]：FTP 帐户中位置的描述。

* [!UICONTROL **目录路径**]：FTP 帐户中位置的路径。

### SFTP

提供了对 Data Warehouse 的 SFTP 支持。需要 SFTP 主机、用户名，以及包含有效 RSA 或 DSA 公钥的目标站点。您可以在创建 Data Warehouse 目标时下载相应的公钥。

填写可用字段时，请使用以下信息：

#### 帐户字段

* [!UICONTROL **帐户名称**]：FTP 帐户的名称。

* [!UICONTROL **帐户描述**]：FTP 帐户的描述。

* [!UICONTROL **主机名**]：输入所需的 SFTP 目标 URL。例如，`sftp.company.com`。

  >[!NOTE]
  >
  >  不要在 URL 的开头包括 `sftp://`。

* [!UICONTROL **用户名**]：输入用于登录 SFTP 网站的用户名。

* [!UICONTROL **上传期间使用临时文件扩展名**]：启用此选项后，上传过程中将使用 `.part` 文件扩展名。将此选项保持启用状态，除非您的 SFTP 服务器禁止在上传完文件后更改文件名。

* [!UICONTROL **公钥**]：创建 Data Warehouse 目标时下载相应公钥。

#### 位置字段

* [!UICONTROL **位置名称**]：要将文件发送到的 SFTP 帐户中位置的名称。

* [!UICONTROL **位置描述**]：SFTP 帐户中位置的描述。

* [!UICONTROL **目录路径**]：SFTP 帐户中位置的路径。

有关 SFTP 配置的更多信息，请参阅[将 Data Warehouse 请求发送到 SFTP 服务器](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md)。

### S3

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

### Azure Blob

Data Warehouse 支持 Azure Blob 目标。需要容器、帐户和密钥。Amazon 会自动加密静态数据。当您下载数据时，数据会自动解密。有关详细信息，请参阅 Microsoft Azure 文档中的[创建存储帐户](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必须实施自己的流程来管理 Data Warehouse 目标上的磁盘空间。Adobe 不会从服务器中删除任何数据。
