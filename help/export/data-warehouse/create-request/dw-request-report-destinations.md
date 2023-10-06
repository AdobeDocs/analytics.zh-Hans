---
description: 描述如何创建 Data Warehouse 请求的步骤。
title: 为Data Warehouse请求配置报表目标
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: f1264344a380944946ffa7b427db7bbc3ea96b1f
workflow-type: tm+mt
source-wordcount: '2255'
ht-degree: 15%

---

# 为Data Warehouse请求配置报表目标

>[!AVAILABILITY]
>
>本文中介绍的一些Data Warehouse功能(以及此部分中的其他Data Warehouse文章)仅在版本的有限测试阶段提供，并且在您的环境中可能尚未提供。
>
>有关尚未向所有客户提供的功能的信息，以及有关这些功能发布时间线的信息，请参阅 [发行说明](/help/release-notes/latest.md).
>
>当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。

创建Data Warehouse请求时，有多种可用的配置选项。 以下信息介绍了如何为请求配置报表目标。

有关如何开始创建请求以及指向其他重要配置选项的链接的信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>配置报表目标时，请考虑以下事项：
>
>* 我们建议使用云帐户或电子邮件作为报表目标。 旧版FTP和SFTP帐户可用，但不建议使用。
>
>* Cloud帐户与您的Adobe Analytics用户帐户相关联。 其他用户无法使用或查看您配置的云帐户。
>
>* 您之前的任何云帐户 [为数据馈送配置](/help/export/analytics-data-feed/create-feed.md) 可用于Data Warehouse。
>
>* 配置的云帐户 [导入Adobe Analytics分类数据](/help/components/locations/locations-manager.md) 配置报表目标时，可以使用来自云目标的报表包。 但是，无法使用为导入分类数据而配置的任何位置。

要配置发送Data Warehouse报告的目标，请执行以下操作：

1. 通过在Adobe Analytics中选择 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **添加**].

   有关其他详细信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在“新建Data Warehouse请求”页面上，选择 [!UICONTROL **报表目标**] 选项卡。

   ![“报表目标”选项卡](assets/dw-report-destination.png)

1. （视情况而定）如果您之前已配置要用作报表目标的帐户（以及该帐户上的目标）：

   1. 从中选择帐户 [!UICONTROL **选择帐户**] 下拉菜单。

      您为配置的任意云帐户 [导入Adobe Analytics分类数据](/help/components/locations/locations-manager.md) 来自云目标的配置信息显示在此处，并可使用。 但是，无法使用为导入分类数据而配置的任何位置。 请按照以下所述添加新目标。

   1. 从中选择与帐户关联的目标 [!UICONTROL **选择目标**] 下拉菜单。 <!-- Is this correct? -->

1. （视情况而定）如果您以前未配置帐户：

   1. 选择 [!UICONTROL **添加帐户**]，然后指定以下信息：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **帐户类型**] | 选择您的云帐户类型。 我们建议为每个帐户类型拥有一个帐户，并根据需要在该帐户中放置多个位置。 <p>选择帐户类型后，将会显示特定于该帐户类型的字段。 </p> |
      | [!UICONTROL **帐户名称**] | 指定帐户的名称。 创建位置时将显示此名称。 <!-- true? --> |
      | [!UICONTROL **帐户描述**] | 提供帐户的简短描述，以帮助将其与同一帐户类型的其他帐户区分开来。 |

      有关配置说明，请展开以下对应于 [!UICONTROL **帐户类型**] 你选择的。

      配置报表目标时，请使用以下任一帐户类型。 有关配置说明，请展开帐户类型。 (其他 [旧目标](#legacy-destinations) 也可用，但不推荐。)

      +++Amazon S3

      指定以下信息以配置Amazon S3角色ARN帐户：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **角色 ARN**] | 您必须提供一个角色ARN(Amazon资源名称)，Adobe可以使用该角色来访问Amazon S3帐户。 为此，您需要为源帐户创建IAM权限策略，将策略附加到用户，然后为目标帐户创建角色。 有关具体信息，请参阅 [此AWS文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
      | [!UICONTROL **用户 ARN**] | 用户ARN(Amazon资源名称)由Adobe提供。 您必须将此用户附加到您创建的策略。 |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      指定以下信息来配置Google Cloud Platform帐户：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **项目ID**] | 您的Google Cloud项目ID。 请参阅 [Google Cloud有关获取项目ID的文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      指定以下信息以配置Azure SAS帐户：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **密钥保管库 URI**] | <p>Azure密钥库中SAS令牌的路径。  要配置Azure SAS，您需要使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参见 [有关如何分配密钥保管库访问策略的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
      | [!UICONTROL **密钥保管库机密名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥库的 **密钥库** 设置页面。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **机密**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      指定以下信息以配置Azure RBAC帐户：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **机密**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

+++

      +++电子邮件

      指定以下信息以配置电子邮件帐户：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **收件人**] | 发送报告时，可以向特定用户发送电子邮件通知。指定单个电子邮件地址或以逗号分隔的电子邮件地址列表。 <!-- How does this differ from the Notification email tab? --> |

   1. 选择 [!UICONTROL **添加位置**]，然后指定以下信息： |字段 |函数 | ------------------- | [!UICONTROL **名称**] |位置的名称。  | | [!UICONTROL **描述**] |提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。 | | [!UICONTROL **位置帐户**] |选择您在中创建的位置帐户 [添加帐户](#add-an-account). |

   1. 在 [!UICONTROL **位置属性**] 部分，指定特定于您的位置帐户的帐户类型的信息。

      有关配置说明，请展开以下对应于 [!UICONTROL **帐户类型**] 您之前选择的内容。

      +++Amazon S3

      指定以下信息以配置Amazon S3位置：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **存储桶名称**] | Amazon S3帐户中要将Adobe Analytics数据发送到的存储段。 确保Adobe提供的用户ARN有权将文件上传到此存储段。 |
      | [!UICONTROL **密钥前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如， folder_name/ |

      {style="table-layout:auto"}

+++

      +++Google Cloud Platform

      指定以下信息来配置Google Cloud Platform位置：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **存储桶名称**] | GCP帐户中要将Adobe Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 有关授予权限的信息，请参见 [将主体添加到存储段级别策略](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) 在Google Cloud文档中。 |
      | [!UICONTROL **密钥前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如， folder_name/ |

      {style="table-layout:auto"}

+++

      +++Azure SAS

      指定以下信息以配置Azure SAS位置：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **容器名称**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 |
      | [!UICONTROL **密钥前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

      {style="table-layout:auto"}

+++

      +++Azure RBAC

      指定以下信息以配置Azure RBAC位置：

      | 字段 | 函数 |
      |---------|----------|
      | [!UICONTROL **容器名称**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 确保授予将文件上载到您之前创建的Azure应用程序的权限。 |
      | [!UICONTROL **密钥前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |
      | [!UICONTROL **帐户名称**] | Azure存储帐户。 |

      {style="table-layout:auto"}

+++

   1. 选择&#x200B;[!UICONTROL **保存**]。

      您现在可以将数据导入到您配置的帐户和位置。

1. 继续在上配置您的Data Warehouse请求 [!UICONTROL **报表选项**] 选项卡。 有关更多信息，请参阅 [为Data Warehouse请求配置报表选项](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## 旧版目标

>[!IMPORTANT]
>
>此部分介绍的目标是旧版目标，不建议使用。 因此，在创建数据仓库目标时，请使用以下目标之一： Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS或电子邮件。 有关每个推荐目标的详细信息，请参阅以上信息。

以下信息提供了每个旧版目标的配置信息：

### FTP

Data Warehouse数据可以传送到Adobe或客户托管的FTP位置。 需要 FTP 主机、用户名和密码。可使用路径字段将馈送文件放置在文件夹中。文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。

填写可用字段时，请使用以下信息：

#### 帐户字段

* [!UICONTROL **帐户名称**]：FTP帐户的名称。

* [!UICONTROL **帐户描述**]：FTP帐户的描述。

* [!UICONTROL **主机名**]：输入所需的FTP目标URL。 例如：`ftp.company.com`。

  >[!NOTE]
  >
  >  不包括 `ftp://` 在URL的开头处。

* [!UICONTROL **用户名**]：输入用户名以登录到FTP站点。

* [!UICONTROL **密码和确认密码**]：输入登录FTP站点的密码。

#### 位置字段

* [!UICONTROL **位置名称**]：您希望发送文件的FTP帐户上的位置名称。

* [!UICONTROL **位置描述**]：FTP帐户上位置的描述。

* [!UICONTROL **目录路径**]：FTP帐户上位置的路径。

### SFTP

提供了对Data Warehouse的SFTP支持。 需要 SFTP 主机、用户名，以及包含有效 RSA 或 DSA 公钥的目标站点。创建数据仓库目标时，您可以下载相应的公钥。

填写可用字段时，请使用以下信息：

#### 帐户字段

* [!UICONTROL **帐户名称**]：FTP帐户的名称。

* [!UICONTROL **帐户描述**]：FTP帐户的描述。

* [!UICONTROL **主机名**]：输入所需的SFTP目标URL。 例如：`sftp.company.com`。

  >[!NOTE]
  >
  >  不包括 `sftp://` 在URL的开头处。

* [!UICONTROL **用户名**]：输入用户名以登录SFTP站点。

* [!UICONTROL **公钥**]：创建Data Warehouse目标时下载相应的公钥。

#### 位置字段

* [!UICONTROL **位置名称**]：您希望发送文件的SFTP帐户上的位置名称。

* [!UICONTROL **位置描述**]：SFTP帐户上的位置描述。

* [!UICONTROL **目录路径**]：SFTP帐户上位置的路径。

### S3

您可以将仓库数据直接发送到Amazon S3存储段。 此目标类型需要存储段名称、访问密钥 ID 和密钥。有关详细信息，请参阅 Amazon S3 文档中的 [Amazon S3 存储段命名要求](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)。

您为上传Data Warehouse数据提供的用户必须具备以下条件 [权限](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

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

数据仓库支持Azure Blob目标。 需要容器、帐户和密钥。Amazon 会自动加密静态数据。当您下载数据时，数据会自动解密。有关详细信息，请参阅 Microsoft Azure 文档中的[创建存储帐户](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必须实施自己的流程来管理数据仓库目标上的磁盘空间。 Adobe 不会从服务器中删除任何数据。
