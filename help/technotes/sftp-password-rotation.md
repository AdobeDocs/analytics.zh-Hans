---
title: FTP和SFTP服务器的安全要求
description: 了解FTP和SFTP服务器的安全要求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 94059a3b7d667fafe1900a4a9c82ed931d769df1
workflow-type: tm+mt
source-wordcount: '1933'
ht-degree: 3%

---

# FTP和SFTP服务器的安全要求

本页介绍了接收Adobe Analytics数据馈送或Data Warehouse交付的数据的现有FTP和SFTP服务器的安全要求。

* **现有FTP服务器**：必须升级为使用SFTP，如下节所述，[升级FTP服务器以使用SFTP](#upgrade-ftp-servers-to-use-sftp)。

  需要从FTP升级到SFTP，因为SFTP可提高安全性。

  或者，为了获得更高级别的安全性，您可以转换为现代云目标。 （有关详细信息，请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。）

* **现有SFTP服务器（和新升级的SFTP服务器）**：必须轮换旧密码，如下节所述，[轮换SFTP密码](#rotate-your-sftp-password)。

  定期轮换SFTP密码是有助于保护数据的安全最佳实践。

>[!IMPORTANT]
>
>完成本文中的步骤之前，请考虑以下情况。
>
>* **Adobe建议尽可能转换到新版Cloud目标，而不是升级到SFTP。**
>FTP和SFTP是旧版目标类型。 Adobe建议迁移到现代云目标类型（例如Amazon S3、Google Cloud Platform或Azure），而不是像本文所述将FTP帐户升级到SFTP和轮换SFTP密码。 这些云目标提供了更高级别的安全性。 有关详细信息，请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果FTP和SFTP帐户仅用于分类，请迁移到分类集。**
>如果您的FTP或SFTP帐户专门用于分类，则您应该从&#x200B;**分类导入器**&#x200B;迁移到&#x200B;**分类集**，而不是按照本文中的说明将FTP帐户升级到SFTP并轮换SFTP密码。 分类导入器将被弃用，在&#x200B;**2026年8月31日**&#x200B;后无法再访问。 有关详细信息，请参阅[分类集概述](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview)。

## 先决条件

### 清点FTP帐户

对于与数据馈送或Data Warehouse一起使用的每个FTP站点，您必须完成本页面上的SFTP升级步骤。

因此，您必须确定正在接收数据馈送或Data Warehouse数据的所有FTP帐户。 此信息显示在FTP配置设置中，如[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)中的[旧帐户类型](/help/components/locations/configure-import-accounts.md#configure-a-location-account)部分所述。

针对每个帐户，收集以下信息：

* **主机**：您的帐户连接到的FTP服务器的主机名（例如，`ftp.omniture.com`、`ftp2.omniture.com`等）。

* **端口**：使用Adobe托管的SFTP服务器时，SFTP客户端连接到端口22。 不安全的FTP连接使用端口21。

* **用户名**：用于登录到FTP服务器的用户名。

* **位置帐户密码**：帐户的当前帐户密码。 这是您在下载发送到您的FTP位置的数据时当前使用的帐户密码。 Adobe Analytics界面中没有此信息。

### 确认您可以在工具中更新凭据

确保您可以在用于连接到SFTP站点的任何工具或脚本（例如，SFTP客户端、自动脚本或第三方平台）中更新SFTP密码。

所有客户端都应通过SFTP连接，并使用密码作为后备。

## 升级FTP服务器以使用SFTP

>[!IMPORTANT]
>
>如果您的FTP数据交付给第三方合作伙伴（例如，咨询公司或分析供应商），请在执行以下步骤之前与他们协调。

### 步骤1：生成组织的SSH密钥以下载数据

本节介绍如何生成组织的SSH密钥（公钥/私钥对），这些密钥用于从SFTP服务器&#x200B;**下载数据**。

>[!NOTE]
>
>在将来的步骤中，您将下载Adobe提供的另一个公钥。 这是第二个公钥/私钥对的一部分，Adobe使用该密钥对&#x200B;**将数据**&#x200B;上传到SFTP服务器。

要设置安全传输以从FTP服务器下载数据，请执行以下操作：

1. 登录到可从FTP服务器下载数据的工作站。

1. 生成公钥/私钥对以用于安全传输。

   使用Adobe托管的SFTP服务器时，Adobe支持RSA和ed25519密钥。

   * **在Linux环境中**：运行以下命令以生成ed25519密钥对：

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     如果您的策略不允许使用ed25519密钥，请运行以下命令来生成RSA密钥对：

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **在Windows环境中**：使用PuTTYgen。

1. 创建名为 [!DNL `authorized_keys`] 的文件（无扩展名）。

1. 将公钥的内容复制到[!DNL `authorized_keys`]文件中。

1. 在将来的步骤中，您将返回此[!DNL `authorized_keys`]文件以添加Adobe的公共密钥，Adobe使用该密钥将数据上载到SFTP服务器。 然后将[!DNL `authorized_keys`]文件添加到SFTP服务器。

### 步骤2：在Adobe Analytics中创建新的SFTP位置帐户

创建新的SFTP位置帐户以替换每个现有的FTP帐户。

创建新的SFTP位置帐户时，必须使用要替换的现有FTP帐户中使用的相同主机名和用户名。

>[!NOTE]
>
>在将来的步骤中，您将配置此新位置帐户，以将其用作数据馈送和Data Warehouse交付的目标。

#### 创建SFTP帐户

1. 在Adobe Analytics中，转到&#x200B;[!UICONTROL **组件**] > [!UICONTROL **位置**]。

1. 选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

1. 选择&#x200B;[!UICONTROL **添加帐户**]。

1. 在&#x200B;[!UICONTROL **帐户类型**]&#x200B;下拉菜单中，选择&#x200B;[!UICONTROL **SFTP（旧版）**]。

1. 请完成以下字段：

   | 字段名称 | 功能 |
   |---------|----------|
   | [!UICONTROL **主机名**] | 您的SFTP主机名（例如，`ftp.omniture.com`）。 |
   | [!UICONTROL **端口**] | 用于发送数据的防火墙端口。 这是Adobe托管的SFTP连接的端口22。 |
   | [!UICONTROL **用户名**] | SFTP用户名。 使用与您的FTP帐户相同的用户名。 |

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 在&#x200B;[!UICONTROL **创建的帐户**]&#x200B;对话框中，下载RSA或ed25519公钥，然后选择&#x200B;[!UICONTROL **确定**]。 这是Adobe用于将数据上传到SFTP服务器的SSH公钥。 （在以下部分[将Adobe的SSH公钥添加到SFTP服务器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此密钥。）

1. 对要创建的每个SFTP帐户重复此过程。

1. 继续下面的部分，[将公钥上传到SFTP服务器](#upload-the-public-key-to-the-sftp-server)。

#### 将Adobe的SSH公钥添加到[!DNL `authorized_keys`]文件并将其上传到FTP服务器

您在上一节的步骤7中下载的公钥是Adobe用于&#x200B;**将数据上传**&#x200B;到SFTP服务器的公钥/私钥对的一部分。

您需要将此公钥添加到您之前在其中添加您组织的下载密钥的[!DNL `authorized_keys`]文件中（您在[步骤1：生成您组织的SSH密钥以下载数据](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)）中。

要将Adobe的SSH公钥添加到[!DNL `authorized_keys`]文件并将其上载到FTP服务器，请执行以下操作：

1. 登录到可从FTP服务器下载数据的工作站。

1. 打开[!DNL `authorized_keys`]文件并添加Adobe的上传密钥。 此文件应已包含贵组织的下载密钥，该密钥来自[步骤1：生成贵组织的SSH密钥以下载数据](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)。

1. 将[!DNL `authorized_keys`]文件上传到FTP服务器：

   1. 连接到FTP服务器并使用您的用户名和密码登录。
这可以是由Adobe托管的FTP服务器或您自己的FTP服务器。
   1. 创建一个 [!DNL .ssh] 目录（如果没有）。
   1. 将 [!DNL `authorized_keys`] 文件上传到 [!DNL .ssh] 目录。

1. 更新防火墙设置以允许来自SFTP服务器的入站连接。 使用Adobe托管的SFTP服务器时，请允许来自端口22上Adobe IP范围的入站连接。

1. 通过使用SFTP客户端登录到服务器来测试连接。

1. 对您在上一节[创建SFTP帐户](#create-the-sftp-account)中创建的每个SFTP帐户重复此过程。

1. 继续下面的部分，[在帐户](#add-a-location-within-the-account)中添加位置。

#### 在帐户中添加位置

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;选项卡上，选择&#x200B;[!UICONTROL **添加位置**]。

1. 指定名称、描述，以及此位置是将与数据馈送还是Data Warehouse一起使用。

1. 在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中，选择您刚刚创建的帐户。

1. 在&#x200B;[!UICONTROL **目录路径**]&#x200B;字段中，指定SFTP服务器上目录的路径。 路径中的文件夹必须已存在；否则，会发生错误。 例如，`/folder_name/folder_name`。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 为您创建的每个SFTP帐户重复此过程。

有关详细说明，请参阅[配置云导入和导出位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations)。

### 步骤3：编辑数据馈送和Data Warehouse请求以使用新的SFTP目标

更新当前将数据发送到FTP目标的任何现有计划数据馈送和Data Warehouse请求，以使用您创建的新SFTP目标。

#### 编辑数据馈送

编辑配置了旧FTP目标的每个计划数据馈送，以使用新的SFTP目标：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

1. 找到要编辑的数据馈送。 若要查找数据馈送，您可以[筛选和搜索数据馈送列表](#filter-and-search-the-list-of-data-feeds)。

1. 在&#x200B;[!UICONTROL **馈送名称**]&#x200B;列中选择数据馈送。

   将显示&#x200B;[!UICONTROL **编辑&#x200B;_馈送名称_**]页面。

1. 在&#x200B;[!UICONTROL **目标**]&#x200B;部分的&#x200B;[!UICONTROL **帐户**]&#x200B;字段中，使用下拉菜单选择您创建的新SFTP目标。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;字段中，使用下拉菜单选择SFTP帐户中的位置。

1. 选择&#x200B;[!UICONTROL **保存**]。

有关详细信息，请参阅[管理数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md)中的[编辑数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)。

#### 编辑Data Warehouse请求

编辑每个配置了旧FTP目标的计划Data Warehouse请求，以使用新的SFTP目标：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在Data Warehouse页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **编辑**]。

1. 选择&#x200B;[!UICONTROL **报告目标**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **帐户**]&#x200B;字段中，使用下拉菜单选择您创建的新SFTP目标。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;字段中，使用下拉菜单选择SFTP帐户中的位置。

1. 选择&#x200B;[!UICONTROL **保存更改**]。

有关详细信息，请参阅[管理Data Warehouse请求](/help/export/data-warehouse/data-warehouse-requests-manage.md)中的[编辑请求](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)。

### 步骤4：更新防火墙设置

如果尚未更新，则需要按如下方式更新防火墙设置：

* **使用Adobe的FTP服务器时**：您需要更新防火墙设置以允许端口22上的&#x200B;**出站**&#x200B;连接。

* **使用您自己的FTP服务器时**：您需要更新防火墙设置，以便在您托管服务的任何端口（通常是端口22）上允许&#x200B;**入站**&#x200B;连接。

您还应该删除旧的FTP专用规则，例如允许端口21上的入站连接。 (FTP使用端口21，外加一系列用于数据传输的附加端口。 作为安全最佳实践，您最终应删除通过防火墙进行的这种不必要的访问。)

### 步骤5：确保正确提交计划的数据馈送和Data Warehouse请求

在更新每个现有数据馈送和Data Warehouse请求以使用新的SFTP帐户和位置后，等待下一个计划提交。 验证数据是否按预期到达新目标。

### 步骤6：在升级后的SFTP服务器上轮换密码

将FTP服务器升级到SFTP后，还必须轮换SFTP密码，如下节[轮换SFTP密码](#rotate-your-sftp-password)中所述。

## 轮换您的SFTP密码

如果基于密钥的身份验证失败，则SFTP密码将用作回退身份验证方法。

从FTP升级到SFTP后，请尽快轮换SFTP密码。 它应根据您的既定政策继续定期轮换。

1. 联系Adobe客户关怀团队并请求获取新密码。

1. 为每个SFTP帐户提供&#x200B;**主机名**&#x200B;和&#x200B;**用户名**。

   客户关怀团队将为每个FTP帐户生成一个新密码。

1. 更新用于连接到SFTP服务器的客户端中的密码。


