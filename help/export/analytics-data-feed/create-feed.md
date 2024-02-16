---
title: 创建数据馈送
description: 了解如何创建数据馈送。
feature: Data Feeds
exl-id: 36c8a40e-6137-4836-9d4b-bebf17b932bc
source-git-commit: 206f601b2bce76dd51564d839135fbdcea1186fa
workflow-type: tm+mt
source-wordcount: '3215'
ht-degree: 17%

---

# 创建数据馈送

在创建数据馈送时，您可以为Adobe提供：

* 有关要将原始数据文件发送到的目标的信息

* 要包含在每个文件中的数据

>[!NOTE]
>
>在创建数据馈送之前，一定要基本了解数据馈送，并确保满足所有必要的先决条件。 有关更多信息，请参阅 [数据馈送概述](data-feed-overview.md).

## 创建和配置数据馈送

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 选择右上角的9个正方形图标，然后选择 [!UICONTROL **分析**].
1. 在顶部导航栏中，转到 [!UICONTROL **管理员**] > [!UICONTROL **数据馈送**].
1. 选择 [!UICONTROL **添加**].

   ![添加数据馈送](assets/datafeed-add.png)

   此时将显示一个页面，其中包含三个主要类别： [!UICONTROL **馈送信息**]， [!UICONTROL **目标**]、和 [!UICONTROL **数据列定义**].
1. 在 [!UICONTROL **馈送信息**] 部分，请完成以下字段：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **名称**] | 数据馈送的名称。 在选定的报表包中，名称必须是唯一的，且长度最多为 255 个字符。 |
   | [!UICONTROL **报表包**] | 数据馈送所基于的报表包。 如果为同一报表包创建了多个数据馈送，则它们必须具有不同的列定义。只有源报表包支持数据馈送；虚拟报表包则不支持。 |
   | [!UICONTROL **完成时发送电子邮件**] | 在馈送完成处理时要通知的电子邮件地址。 电子邮件地址的格式必须正确。 |
   | [!UICONTROL **馈送间隔**] | 选择 **每日** 用于回填或历史数据。 每日馈送包含一天的数据，从报表包所在时区的午夜到午夜。  选择 **每小时** 用于连续数据（如有需要，也可使用“每日”继续馈送）。 每小时馈送包含一个小时的数据。 |
   | [!UICONTROL **延迟处理**] | 在处理数据馈送文件之前等待给定的时长。 延迟可用于为移动设备实施提供使离线设备变为在线并发送数据的机会。它还可用于在管理以前处理的文件时容纳组织的服务器端进程。在大多数情况下，无需延迟。馈送最多可延迟 120 分钟。 |
   | [!UICONTROL **开始和结束日期**] | 开始日期表示您希望数据馈送开始的日期。 要立即开始处理历史数据的数据馈送，请将此日期设置为过去收集数据的任何日期。 开始日期和结束日期基于报表包所在的时区。 |
   | [!UICONTROL **连续进纸**] | 此复选框将删除结束日期，允许馈送无限期运行。 当馈送完成历史数据处理时，馈送会等待完成给定小时或天的数据收集。当前小时或天结束后，处理将在指定的延迟后开始。 |

1. 在 [!UICONTROL **目标**] 部分，在 [!UICONTROL **类型**] 下拉菜单中，选择要将数据发送到的目标。

   >[!NOTE]
   >
   >配置报表目标时，请考虑以下事项：
   >
   >* 我们建议为您的报表目标使用云帐户。 [旧版FTP和SFTP帐户](#legacy-destinations) 可用，但不推荐。
   >
   >* Cloud帐户与您的Adobe Analytics用户帐户相关联。 其他用户无法使用或查看您配置的云帐户。
   >

   ![数据馈送目标下拉菜单](assets/datafeed-destinations-dropdown.png)

   创建数据馈送时，请使用以下任一目标类型。 有关配置说明，请展开目标类型。 (其他 [旧目标](#legacy-destinations) 也可用，但不推荐。)

   +++Amazon S3

   您可以直接将馈送发送到 Amazon S3 存储段。此目标类型只需要您的Amazon S3帐户和位置（存储段）。

   Adobe Analytics使用跨帐户身份验证将文件从Adobe Analytics上传到Amazon S3实例中的指定位置。

   要将Amazon S3存储段配置为数据馈送的目标，请执行以下操作：

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目标**] 部分，选择 [!UICONTROL **Amazon S3**].

      ![Amazon S3目标](assets/datafeed-destination-amazons3.png)

   1. 选择 [!UICONTROL **选择位置**].

      此时将显示“Amazon S3导出位置”页面。

   1. （视情况而定）如果您之前添加了Amazon S3帐户和位置：

      1. 从中选择帐户 [!UICONTROL **选择帐户**] 下拉菜单。

      1. 从中选择位置 [!UICONTROL **选择位置**] 下拉菜单。

      1. 选择 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         现在，目标已配置为将数据发送到您指定的Amazon S3位置。

   1. （视情况而定）如果您之前未添加Amazon S3帐户：

      1. 选择 [!UICONTROL **添加帐户**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **帐户名称**] | 帐户的名称。 这可以是您选择的任何名称。 |
         | [!UICONTROL **帐户描述**] | 帐户的描述。 |
         | [!UICONTROL **角色ARN**] | 您必须提供一个角色ARN(Amazon资源名称)，Adobe可以使用该角色来访问Amazon S3帐户。 为此，您需要为源帐户创建IAM权限策略，将策略附加到用户，然后为目标帐户创建角色。 有关具体信息，请参阅 [此AWS文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
         | [!UICONTROL **用户ARN**] | 用户ARN(Amazon资源名称)由Adobe提供。 您必须将此用户附加到您创建的策略。 |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **添加位置**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **名称**] | 帐户的名称。 |
         | [!UICONTROL **描述**] | 帐户的描述。 |
         | [!UICONTROL **分段**] | Amazon S3帐户中要将Adobe Analytics数据发送到的存储段。 <p>确保Adobe提供的用户ARN具有 `S3:PutObject` 权限以将文件上传到此存储段。 此权限允许用户ARN上传初始文件并覆盖文件以供后续上传。</p> |
         | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **创建**] > [!UICONTROL **保存**].

         现在，目标已配置为将数据发送到您指定的Amazon S3位置。

+++

   +++Azure RBAC

   您可以使用RBAC身份验证将馈送直接发送到Azure容器。 此目标类型需要应用程序ID、租户ID和密码。

   要将Azure RBAC帐户配置为数据馈送的目标，请执行以下操作：

   1. 如果还没有该应用程序，请创建Adobe Analytics可用于身份验证的Azure应用程序，然后在访问控制(IAM)中授予访问权限。

      有关信息，请参阅 [有关如何创建Azure Active Directory应用程序的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目标**] 部分，选择 [!UICONTROL **Azure RBAC**].

      ![Azure RBAC目标](assets/datafeed-destination-azurerbac.png)

   1. 选择 [!UICONTROL **选择位置**].

      此时将显示“Azure RBAC导出位置”页面。

   1. （视情况而定）如果您之前添加了Azure RBAC帐户和位置：

      1. 从中选择帐户 [!UICONTROL **选择帐户**] 下拉菜单。

      1. 从中选择位置 [!UICONTROL **选择位置**] 下拉菜单。

      1. 选择 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的Azure RBAC位置。

   1. （视情况而定）如果您以前未添加Azure RBAC帐户：

      1. 选择 [!UICONTROL **添加帐户**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **帐户名称**] | Azure RBAC帐户的名称。 此名称显示在 [!UICONTROL **选择帐户**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **帐户描述**] | Azure RBAC帐户的描述。 此描述显示在 [!UICONTROL **选择帐户**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **应用程序Id**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **租户ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **添加位置**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **名称**] | 位置的名称。 此名称显示在 [!UICONTROL **选择位置**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **描述**] | 位置的描述。 此描述显示在 [!UICONTROL **选择位置**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **帐户**] | Azure存储帐户。 |
         | [!UICONTROL **容器**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 确保授予将文件上载到您之前创建的Azure应用程序的权限。 |
         | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **创建**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的Azure RBAC位置。

+++

   +++Azure SAS

   您可以使用SAS身份验证将馈送直接发送到Azure容器。 此目标类型需要应用程序ID、租户ID、密钥保管库URI、密钥保管库密钥名和密钥。

   要将Azure SAS配置为数据馈送的目标，请执行以下操作：

   1. 如果尚未这样做，请创建一个Adobe Analytics可用于身份验证的Azure应用程序。

      有关信息，请参阅 [有关如何创建Azure Active Directory应用程序的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目标**] 部分，选择 [!UICONTROL **Azure SAS**].

      ![Azure SAS目标](assets/datafeed-destination-azuresas.png)

   1. 选择 [!UICONTROL **选择位置**].

      此时将显示“Azure SAS导出位置”页面。

   1. （视情况而定）如果您之前添加了Azure SAS帐户和位置：

      1. 从中选择帐户 [!UICONTROL **选择帐户**] 下拉菜单。

      1. 从中选择位置 [!UICONTROL **选择位置**] 下拉菜单。

      1. 选择 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的Azure SAS位置。

   1. （视情况而定）如果您以前未添加Azure SAS帐户：

      1. 选择 [!UICONTROL **添加帐户**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **帐户名称**] | Azure SAS帐户的名称。 此名称显示在 [!UICONTROL **选择帐户**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **帐户描述**] | Azure SAS帐户的描述。 此描述显示在 [!UICONTROL **选择帐户**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **应用程序Id**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **租户ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
         | [!UICONTROL **密钥保险库URI**] | <p>Azure密钥库中SAS令牌的路径。  要配置Azure SAS，您需要使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参见 [有关如何分配密钥保管库访问策略的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
         | [!UICONTROL **密钥保管库秘密名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥库的 **密钥库** 设置页面。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
         | [!UICONTROL **密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **添加位置**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **名称**] | 位置的名称。 此名称显示在 [!UICONTROL **选择位置**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **描述**] | 位置的描述。 此描述显示在 [!UICONTROL **选择位置**] 下拉字段，可以是您选择的任意名称。 |
         | [!UICONTROL **容器**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 |
         | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **创建**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的Azure SAS位置。

+++

   +++Google云平台

   您可以直接将馈送发送到Google Cloud Platform (GCP)存储桶。 此目标类型只需要您的GCP帐户名称和位置（存储段）名称。

   Adobe Analytics使用跨帐户身份验证将文件从Adobe Analytics上传到GCP实例中的指定位置。

   要将GCP存储段配置为数据馈送的目标，请执行以下操作：

   1. 在Adobe Analytics Admin Console的 [!UICONTROL **目标**] 部分，选择 [!UICONTROL **Google Cloud平台**].

      ![Google Cloud平台目标](assets/datafeed-destination-gcp.png)

   1. 选择 [!UICONTROL **选择位置**].

      此时将显示“GCP导出位置”页。

   1. （视情况而定）如果您之前添加了GCP帐户和位置：

      1. 从中选择帐户 [!UICONTROL **选择帐户**] 下拉菜单。

      1. 从中选择位置 [!UICONTROL **选择位置**] 下拉菜单。

      1. 选择 [!UICONTROL **保存**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的GCP位置。

   1. （视情况而定）如果您以前未添加GCP帐户：

      1. 选择 [!UICONTROL **添加帐户**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **帐户名称**] | 帐户的名称。 这可以是您选择的任何名称。 |
         | [!UICONTROL **帐户描述**] | 帐户的描述。 |
         | [!UICONTROL **项目ID**] | 您的Google Cloud项目ID。 请参阅 [Google Cloud有关获取项目ID的文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **添加位置**]，然后指定以下信息：

         | 字段 | 函数 |
         |---------|----------|
         | [!UICONTROL **主体**] | 主体由Adobe提供。 您必须授予权限才能接收此主体的源。 |
         | [!UICONTROL **名称**] | 帐户的名称。 |
         | [!UICONTROL **描述**] | 帐户的描述。 |
         | [!UICONTROL **分段**] | GCP帐户中要将Adobe Analytics数据发送到的存储段。 <p>确保您已向Adobe提供的承担者授予以下任一权限：<ul><li>`roles/storage.objectCreator`：如果要将承担者限制为仅在GCP帐户中创建文件，请使用此权限。 </br>**重要提示：** 如果将此权限用于计划报告，则必须对每个新的计划导出使用唯一的文件名。 否则，报告生成将失败，因为主体无权覆盖现有文件。</li><li>（推荐） `roles/storage.objectUser`：如果您希望承担者有权查看、列出、更新和删除GCP帐户中的文件，请使用此权限。</br>此权限允许承担者覆盖现有文件以进行后续上传，而无需为每个新的计划导出自动生成唯一的文件名。</li></ul><p>有关授予权限的信息，请参见 [将主体添加到存储段级别策略](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) 在Google Cloud文档中。</p> |
         | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

         {style="table-layout:auto"}

      1. 选择 [!UICONTROL **创建**] > [!UICONTROL **保存**].

         目标现在配置为将数据发送到您指定的GCP位置。

+++

1. 在  [!UICONTROL **数据列定义**] 部分，选择最新的 [!UICONTROL **所有Adobe Columns**] 模板，然后完成以下字段：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **删除转义字符**] | 在收集数据时，某些字符（如换行符）可能会导致问题。 如果您希望从馈送文件中删除这些字符，请选中此框。 |
   | [!UICONTROL **压缩格式**] | 使用的压缩类型。 **Gzip** 输出文件 `.tar.gz` 格式。 **Zip** 输出文件 `.zip` 格式。 |
   | [!UICONTROL **包装类型**] | 选择 **多个文件** 用于大多数数据馈送。 此选项会将您的数据分页为未压缩的2 GB块。 （如果选择了多个文件，且报表时间范围的未压缩数据小于2 GB，则会发送一个文件。） 选择 **单个文件** 输出 `hit_data.tsv` 文件合并为一个可能非常庞大的文件。 |
   | [!UICONTROL **清单**] | Adobe是否应该投放 [清单文件](c-df-contents/datafeeds-contents.md#feed-manifest) 在馈送间隔内未收集到数据时发送到目标。 如果您选择 **清单文件**，则在未收集到数据时会收到类似于以下内容的清单文件：<p>`text`</p><p>`Datafeed-Manifest-Version: 1.0`</p><p>`Lookup-Files: 0`</p><p>`Data-Files: 0`</p><p> `Total-Records: 0`</p> |
   | [!UICONTROL **列模板**] | 创建多个数据馈送时，Adobe建议创建列模板。 选择列模板会自动包含模板中指定的列。默认情况下，Adobe 也提供了多个模板。 |
   | [!UICONTROL **可用列**] | Adobe Analytics中的所有可用数据列。 单击“[!UICONTROL 全部添加]”可在数据馈送中包含所有列。 |
   | [!UICONTROL **包含的列**] | 要包含在数据馈送中的列。 单击“[!UICONTROL 全部移除]”可从数据馈送中移除所有列。 |
   | [!UICONTROL **下载 CSV**] | 下载包含所有包含的列的CSV文件。 |

1. 选择 [!UICONTROL **保存**] 右上角。

   历史数据处理将立即开始。 当完成一天的数据处理时，文件将发送到您配置的目标。

   有关如何访问数据馈送以及更好地了解其内容的信息，请参阅 [数据馈送内容 — 概述](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md).

## 旧版目标

>[!IMPORTANT]
>
>此部分介绍的目标是旧版目标，不建议使用。 因此，在创建数据馈送时，请使用以下目标之一： Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS。 请参阅 [创建和配置数据馈送](#create-and-configure-a-data-feed) 以了解有关每个推荐目标的详细信息。


以下信息提供了每个旧版目标的配置信息：

### FTP

数据馈送数据可以提交到Adobe或客户托管的FTP位置。 需要 FTP 主机、用户名和密码。可使用路径字段将馈送文件放置在文件夹中。文件夹必须已存在；如果指定的路径不存在，则馈送将引发错误。

填写可用字段时，请使用以下信息：

* [!UICONTROL **主机**]：输入所需的FTP目标URL。 例如：`ftp://ftp.omniture.com`。
* [!UICONTROL **路径**]：可留空
* [!UICONTROL **用户名**]：输入用户名以登录到FTP站点。
* [!UICONTROL **密码和确认密码**]：输入登录FTP站点的密码。

### SFTP

提供了对数据馈送的 SFTP 支持。需要 SFTP 主机、用户名，以及包含有效 RSA 或 DSA 公钥的目标站点。您可以在创建馈送时下载相应的公钥。

### S3

您可以直接将馈送发送到 Amazon S3 存储段。此目标类型需要存储段名称、访问密钥 ID 和密钥。有关详细信息，请参阅 Amazon S3 文档中的 [Amazon S3 存储段命名要求](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html)。

您为上传数据馈送提供的用户必须具有以下[权限](https://docs.aws.amazon.com/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html)：

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

  >[!NOTE]
  >
  >每次上传到 Amazon S3 存储桶时，无论存储桶是否有需要它的策略，[!DNL Analytics] 都会将存储桶所有者添加到 BucketOwnerFullControl ACL。有关更多信息，请参阅&quot;[什么是Amazon S3数据馈送的BucketOwnerFullControl？](df-faq.md#BucketOwnerFullControl)&quot;

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

数据馈送支持 Azure Blob 目标。需要容器、帐户和密钥。Amazon 会自动加密静态数据。当您下载数据时，数据会自动解密。有关详细信息，请参阅 Microsoft Azure 文档中的[创建存储帐户](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys)。

>[!NOTE]
>
>您必须实施自己的流程来管理馈送目标上的磁盘空间。Adobe 不会从服务器中删除任何数据。
