---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 配置云导入帐户
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: c43d7bbdad0ad0265e038ee273c74bec136f1c72
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 5%

---

# 配置云导入帐户

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

在从云目标导入Adobe Analytics分类数据之前，您需要添加并配置帐户以及您希望收集分类数据的帐户位置。

此过程包括按照本文所述添加和配置帐户(例如Amazon S3角色ARN、Google Cloud Platform等)，然后按照所述添加和配置该帐户内的位置（例如帐户内的文件夹） [配置云导入位置](/help/components/locations/configure-import-locations.md).

您需要为Adobe Analytics配置访问云目标帐户所需的信息。

要配置云导入帐户，请执行以下操作：

1. 在Adobe Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **位置**].
1. 在 [!UICONTROL 位置] 页面上，选择 [!UICONTROL **位置凭据**] 选项卡。
1. 选择 [!UICONTROL **添加帐户**]. <!-- add screenshot? -->

   此时将显示添加帐户对话框。
1. 指定以下信息： |字段 |函数 | ------------------- | [!UICONTROL **位置帐户名称**] |位置帐户的名称。 创建位置时将显示此名称 | | [!UICONTROL **位置帐户说明**] |提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。 | | [!UICONTROL **帐户类型**] |选择您的云帐户类型。 我们建议为每个帐户类型拥有一个帐户，并根据需要在该帐户中放置多个位置。 |
1. 在 [!UICONTROL **帐户属性**] 部分，指定特定于所选帐户类型的信息。

   有关配置说明，请展开以下对应于 [!UICONTROL **帐户类型**] 你选择的。

   +++Amazon S3 Role ARN

   指定以下信息以配置Amazon S3角色ARN帐户：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必须提供一个角色ARN(Amazon资源名称)，Adobe可以使用该角色来访问Amazon S3帐户。 为此，您需要为源帐户创建IAM权限策略，将策略附加到用户，然后为目标帐户创建角色。 有关具体信息，请参阅 [此AWS文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

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
   | [!UICONTROL **位置帐户密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定以下信息以配置Azure RBAC帐户：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帐户密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 继续 [配置云导入位置](/help/components/locations/configure-import-locations.md).
