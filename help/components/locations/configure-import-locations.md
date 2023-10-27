---
description: 配置云导入帐户和可以上传分类数据的位置
keywords: Analysis Workspace
title: 配置云导入位置
feature: Classifications
exl-id: 55179868-6228-44ff-835c-f4a7b38e929b
source-git-commit: f71b80dce9d447c431130901d86947d23e28d378
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 7%

---

# 配置云导入位置

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

在从云目标导入Adobe Analytics分类数据之前，您需要添加并配置帐户以及您希望收集分类数据的帐户位置。

此过程包括添加和配置帐户(例如Amazon S3角色ARN、Google Cloud Platform等)以及帐户内的位置（例如帐户内的文件夹）。

要配置云导入位置，请执行以下操作：

1. 在添加位置之前，您需要添加帐户。 如果还没有帐户，请按照中的说明添加帐户 [配置云导入帐户](/help/components/locations/configure-import-accounts.md).
1. 在Adobe Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **位置**].
1. 在 [!UICONTROL 位置] 页面上，选择 [!UICONTROL **位置**] 选项卡。
1. 选择 [!UICONTROL **添加位置**]. <!-- add screenshot? -->

   此时将显示“位置”对话框。
1. 指定以下信息： |字段 |函数 | ------------------- | [!UICONTROL **名称**] |位置的名称。  | | [!UICONTROL **描述**] |提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。 | | [!UICONTROL **位置帐户**] |选择您在中创建的位置帐户 [添加帐户](#add-an-account). |

1. 在 [!UICONTROL **位置属性**] 部分，指定特定于您的位置帐户的帐户类型的信息。

   有关配置说明，请展开以下与您在 [!UICONTROL **位置帐户**] 字段。

   +++Amazon S3 Role ARN

   指定以下信息以配置Amazon S3角色ARN位置：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **存储桶名称**] | Amazon S3帐户中要将Adobe Analytics数据发送到的存储段。 |
   | [!UICONTROL **密钥前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定以下信息来配置Google Cloud Platform位置：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **存储桶名称**] | GCP帐户中要将Adobe Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 |
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

   您现在可以从您配置的帐户和位置导入数据。

   导入数据后，数据不会从云目标中删除。

   >[!NOTE]
   >
   >   如果您之前已使用 [用于导入分类的FTP](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md) 到Adobe Analytics，您需要上传FIN文件。 从云帐户导入时不需要此FIN文件。

