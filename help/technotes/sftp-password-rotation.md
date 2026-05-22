---
title: FTP 和 SFTP 服务器的安全要求
description: 了解关于 FTP 和 SFTP 服务器的安全要求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 94059a3b7d667fafe1900a4a9c82ed931d769df1
workflow-type: ht
source-wordcount: '1933'
ht-degree: 100%

---

# FTP 和 SFTP 服务器的安全要求

本页介绍了用于接收 Adobe Analytics 数据馈送或 Data Warehouse 所传递数据的现有 FTP 和 SFTP 服务器的安全要求。

* **现有的 FTP 服务器**：必须升级以使用 SFTP，如下一小节所述，[升级 FTP 服务器以使用 SFTP](#upgrade-ftp-servers-to-use-sftp)。

  从 FTP 升级到 SFTP 是必要的，因为 SFTP 有助于提高安全性。

  或者为了获得更高的安全水平，您也可以转换到一个现代的云目标。（更多信息请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。）

* **现有的 SFTP 服务器（和刚刚升级的 SFTP 服务器）**：必须轮换旧密码，如下一小节所述，[轮换 SFTP 密码](#rotate-your-sftp-password)。

  定期轮换 SFTP 密码是有助于保护数据安全的最佳做法。

>[!IMPORTANT]
>
>完成本文中所述的步骤之前，请先考虑以下情况。
>
>* **Adobe 建议尽可能转换到一个现代的云目标，而不是升级到 SFTP。**
>FTP 和 SFTP 都是旧版目标类型。Adobe 建议迁移到一个现代的云目标类型（例如 Amazon S3、Google Cloud Platform 或 Azure），这比本文中介绍的将 FTP 帐户升级到 SFTP 以及轮换 SFTP 密码的做法更佳。这类云目标能提供更高的安全水平。更多信息请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果 FTP 和 SFTP 帐户仅用于分类，请迁移到分类集。**
>如果您的 FTP 或 SFTP 帐户仅用于分类，您应该从&#x200B;**分类导入器**&#x200B;迁移到&#x200B;**分类集**，而不是按照本文中所述将 FTP 帐户升级到 SFTP 并轮换 SFTP 密码。分类导入器将被弃用，**2026 年 8 月 31 日**&#x200B;以后无法再访问。有关更多信息，请参阅[分类集概述](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/classifications/sets/overview)。

## 先决条件

### 清点您的 FTP 帐户

对于与数据馈送或 Data Warehouse 结合使用的每一个 FTP 站点，您都必须完成本页面上的 SFTP 升级步骤。

因此，您必须确定目前接收数据馈送或 Data Warehouse 数据的所有 FTP 帐户。这个信息显示在您的 FTP 配置设置中，如[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md)中的[旧帐户类型](/help/components/locations/configure-import-accounts.md#configure-a-location-account)部分中所述。

为每一个帐户收集以下信息：

* **主机**：您的帐户连接的 FTP 服务器的主机名（例如 `ftp.omniture.com`、`ftp2.omniture.com` 等）。

* **端口**：如果使用 Adobe 托管的 SFTP 服务器，SFTP 客户端连接到端口 22。不安全的 FTP 连接使用端口 21。

* **用户名**：用于登录到 FTP 服务器的用户名。

* **位置帐户密码**：帐户的当前帐户密码。这是您在下载传递到您的 FTP 位置的数据时当前使用的帐户密码。Adobe Analytics 界面中没有这个信息。

### 确认您可以在工具中更新凭据

确保您可以在用于连接到 SFTP 站点（例如 SFTP 客户端、自动脚本或第三方平台）的任何工具或脚本中更新 SFTP 密码。

所有客户端都应通过 SFTP 连接，并使用密码作为后备。

## 升级 FTP 服务器以使用 SFTP

>[!IMPORTANT]
>
>如果您的 FTP 数据传递给第三方合作伙伴（例如咨询公司或分析供应商），请在执行本文中所述步骤之前与他们协调。

### 步骤 1：生成您的组织的 SSH 密钥，以下载数据

本小节介绍了如何生成您的组织的 SSH 密钥（一个公钥/私钥对），用于从 SFTP 服务器&#x200B;**下载数据**。

>[!NOTE]
>
>在未来的某个步骤中，您将下载 Adobe 提供的另一个公钥。这是第二个公钥/私钥对的一部分，Adobe 将其用于将&#x200B;**数据上传**&#x200B;到 SFTP 服务器。

要从您的 FTP 服务器下载数据，请通过下述方法设置安全传输：

1. 登录到您要从 FTP 服务器下载数据的工作站。

1. 生成一个公钥/私钥对，用于进行安全传输。

   如果使用 Adobe 托管的 SFTP 服务器，Adobe 支持 RSA 和 ed25519 密钥。

   * **在 Linux 环境中**：运行以下命令，生成 ed25519 密钥对：

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     如果您的策略不允许使用 ed25519 密钥，请运行以下命令生成 RSA 密钥对：

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **在 Windows 环境中**：使用 PuTTYgen。

1. 创建名为 [!DNL `authorized_keys`] 的文件（无扩展名）。

1. 将公钥的内容复制到 [!DNL `authorized_keys`] 文件中。

1. 在未来的某个步骤中，您将返回到这个 [!DNL `authorized_keys`] 文件以添加 Adobe 的公钥，Adobe 将其用于将数据上载到 SFTP 服务器。然后将 [!DNL `authorized_keys`] 文件添加到 SFTP 服务器。

### 步骤 2：在 Adobe Analytics 中创建新的 SFTP 位置帐户

创建一个新的 SFTP 位置帐户，用于替换每一个现有的 FTP 帐户。

创建新的 SFTP 位置帐户时，必须使用要替换的现有 FTP 帐户中使用的相同主机名和用户名。

>[!NOTE]
>
>在未来的某个步骤中，您将配置这个新的位置帐户，将其用作您的数据馈送和 Data Warehouse 传递的目标。

#### 创建 SFTP 帐户

1. 在 Adobe Analytics 中，前往&#x200B;[!UICONTROL **组件**] > [!UICONTROL **位置**]。

1. 选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

1. 选择&#x200B;[!UICONTROL **添加帐户**]。

1. 在&#x200B;[!UICONTROL **帐户类型**] 下拉菜单中，选择 [!UICONTROL **SFTP（旧版）**]。

1. 请完成以下字段：

   | 字段名称 | 功能 |
   |---------|----------|
   | [!UICONTROL **主机名**] | 您的 SFTP 主机名（例如 `ftp.omniture.com`）。 |
   | [!UICONTROL **端口**] | 数据通过这里发送出去的防火墙端口。这是用于 Adobe 托管的 SFTP 连接的端口 22。 |
   | [!UICONTROL **用户名**] | 您的 SFTP 用户名。使用与您的 FTP 帐户相同的用户名。 |

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 在&#x200B;[!UICONTROL **创建的帐户**]&#x200B;对话框中，下载 RSA 或 ed25519 公钥，然后选择&#x200B;[!UICONTROL **确定**]。这是 Adobe 用于将数据上传到 SFTP 服务器的 SSH 公钥。（您将在下一小节[将 Adobe 的 SSH 公钥添加到 SFTP 服务器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此密钥。）

1. 为您要创建的每一个 SFTP 帐户重复这个过程。

1. 继续下面的部分，[将公钥上传到 SFTP 服务器](#upload-the-public-key-to-the-sftp-server)。

#### 将 Adobe 的 SSH 公钥添加到 [!DNL `authorized_keys`] 文件中，然后将其上传到您的 FTP 服务器

您在上一小节的步骤 7 中下载的公钥是 Adobe 用于将&#x200B;**数据上传**&#x200B;到 SFTP 服务器的公钥/私钥对的一部分。

您需要将这个公钥添加到 [!DNL `authorized_keys`] 文件中，您之前已在这个文件中添加了您组织的下载密钥（就是您在[步骤 1：生成您的组织的 SSH 密钥，以下载数据](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)中生成的密钥）。

按照下述方法将 Adobe 的 SSH 公钥添加到 [!DNL `authorized_keys`] 文件中，并将其上传到您的 FTP 服务器：

1. 登录到您要从 FTP 服务器下载数据的工作站。

1. 打开 [!DNL `authorized_keys`] 文件，添加 Adobe 的上传密钥。这个文件中应该已包含您组织的下载密钥，也就是[步骤 1：生成您的组织的 SSH 密钥，以下载数据](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)中生成的密钥。

1. 将 [!DNL `authorized_keys`] 文件上传到您的 FTP 服务器：

   1. 连接到 FTP 服务器，然后使用您的用户名和密码登录。
这可以是由 Adobe 托管的 FTP 服务器，也可以是您自己的 FTP 服务器。
   1. 创建一个 [!DNL .ssh] 目录（如果没有）。
   1. 将 [!DNL `authorized_keys`] 文件上传到 [!DNL .ssh] 目录。

1. 更新您的防火墙设置，允许来自 SFTP 服务器的入站连接。如果使用 Adobe 托管的 SFTP 服务器，请允许来自端口 22 上 Adobe IP 范围的入站连接。

1. 用您的 SFTP 客户端登录到服务器，测试连接是否正常。

1. 为您在上一小节[创建 SFTP 帐户](#create-the-sftp-account)中创建的每一个 SFTP 帐户重复这个过程。

1. 继续下面的部分，[在帐户中添加位置](#add-a-location-within-the-account)。

#### 在帐户中添加位置

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;选项卡中，选择&#x200B;[!UICONTROL **添加位置**]。

1. 指定名称和描述，以及这个位置将与数据馈送还是 Data Warehouse 结合使用。

1. 在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中，选择您刚刚创建的帐户。

1. 在&#x200B;[!UICONTROL **目录路径**]&#x200B;字段中，指定 SFTP 服务器上目录的路径。路径中的文件夹必须已存在，否则会发生错误。例如，`/folder_name/folder_name`。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 为您创建的每一个 SFTP 帐户重复这个过程。

有关详细说明，请参阅[配置云导入和导出位置](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations)。

### 步骤 3：编辑数据馈送和 Data Warehouse 请求，以使用新的 SFTP 目标

更新当前已计划将数据发送到 FTP 目标的任何数据馈送和 Data Warehouse 请求，以使用您新创建的 SFTP 目标。

#### 编辑数据馈送

编辑配置了旧 FTP 目标的每一个已计划的数据馈送，以使用新的 SFTP 目标：

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

1. 找到您想编辑的数据馈送。要查找某个数据馈送，您可以[筛选和搜索数据馈送列表](#filter-and-search-the-list-of-data-feeds)。

1. 在&#x200B;[!UICONTROL **馈送名称**]&#x200B;一列中选择数据馈送。

   现在会显示&#x200B;[!UICONTROL **编辑&#x200B;_馈送名称_**]页面。

1. 在&#x200B;[!UICONTROL **目标**]&#x200B;部分的&#x200B;[!UICONTROL **帐户**]&#x200B;字段中，通过下拉菜单选择您新创建的 SFTP 目标。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;字段中，通过下拉菜单选择 SFTP 帐户中的位置。

1. 选择&#x200B;[!UICONTROL **保存**]。

有关详细信息，请参阅[管理数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md)中的[编辑数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)。

#### 编辑 Data Warehouse 请求

编辑配置了旧 FTP 目标的每一个已计划的 Data Warehouse 请求，以使用新的 SFTP 目标：

1. 在 Adobe Analytics 中，选择&#x200B;[!UICONTROL **工具**] > [!UICONTROL **Data Warehouse**]。

1. 在 Data Warehouse 页面上，选择您想编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **编辑**]。

1. 选择&#x200B;[!UICONTROL **报告目标**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **帐户**]&#x200B;字段中，通过下拉菜单选择您新创建的 SFTP 目标。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;字段中，通过下拉菜单选择 SFTP 帐户中的位置。

1. 选择&#x200B;[!UICONTROL **保存更改**]。

有关详细信息，请参阅[管理 Data Warehouse 请求](/help/export/data-warehouse/data-warehouse-requests-manage.md)中的[编辑请求](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)。

### 步骤 4：更新您的防火墙设置

如果尚未更新，您需要按下述方法更新防火墙设置：

* **如果使用 Adobe 的 FTP 服务器**：您需要更新防火墙设置，允许端口 22 上的&#x200B;**出站**&#x200B;连接。

* **如果使用您自己的 FTP 服务器**：您需要更新防火墙设置，在您托管服务的端口（通常是端口 22）上允许&#x200B;**入站**&#x200B;连接。

您还应移除旧的 FTP 专用规则，例如允许端口 21 上的入站连接。（FTP 使用端口 21，以及一系列用于数据传输的附加端口。作为安全最佳实践，您最后应移除这种不必要的通过防火墙访问的方式。）

### 步骤 5：确保已计划的数据馈送和 Data Warehouse 请求能正确传递

更新了每一个现有的数据馈送和 Data Warehouse 请求，以使用新的 SFTP 帐户和位置以后，等待进行下一个计划传递。验证数据是否按预期到达了新目标。

### 步骤 6：在升级后的 SFTP 服务器上轮换密码

将 FTP 服务器升级到 SFTP 后，您还必须轮换 SFTP 密码，如下一小节[轮换 SFTP 密码](#rotate-your-sftp-password)中所述。

## 轮换 SFTP 密码

在基于密钥的身份验证失败的情况下，SFTP 密码是一种后备的身份验证方法。

从 FTP 升级到 SFTP 后，请尽快轮换 SFTP 密码。密码应根据您制定的策略持续定期轮换。

1. 联系 Adobe 客户关怀团队，请求获取新密码。

1. 为每一个 SFTP 帐户提供&#x200B;**主机名**&#x200B;和&#x200B;**用户名**。

   客户关怀团队将为每一个 FTP 帐户生成一个新密码。

1. 更新您用于连接到 SFTP 服务器的客户端中的密码。


