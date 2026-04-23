---
title: Security Requirements for FTP and SFTP Servers
description: Learn about security requirements for FTP and SFTP servers.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 9067b57a7436656b6776de08e8411ee0a87f2b20
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 2%

---

# Security requirements for FTP and SFTP servers

This page covers security requirements for existing FTP and SFTP servers that receive data delivered by Adobe Analytics Data Feeds or Data Warehouse.

* **Existing FTP servers**: Must be upgraded to use SFTP, as described in the section below, [Upgrade FTP servers to use SFTP](#upgrade-ftp-servers-to-use-sftp).

  Upgrading from FTP to SFTP is a requirement because SFTP allows for increased security.

  或者，为了获得更高级别的安全性，您可以转换为现代云目标。 （有关详细信息，请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。）

* **现有SFTP服务器（和新升级的SFTP服务器）**：必须轮换旧密码，如下节所述，[轮换SFTP密码](#rotate-your-sftp-password)。

  定期轮换SFTP密码是有助于保护数据的安全最佳实践。

>[!IMPORTANT]
>
>完成本文中的步骤之前，请考虑以下情况。
>
>* **Adobe建议尽可能转换到新版云目标，而不是升级到SFTP。**
>FTP和SFTP是旧版目标类型。 Adobe建议迁移到现代云目标类型（例如Amazon S3、Google Cloud Platform或Azure），而不是像本文所述将FTP帐户升级到SFTP和轮换SFTP密码。 这些云目标提供了更高级别的安全性。 有关详细信息，请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果FTP和SFTP帐户专门用于分类，请迁移到分类集。**
>如果您的FTP或SFTP帐户专门用于分类，则您应该从&#x200B;**分类导入器**&#x200B;迁移到&#x200B;**分类集**，而不是按照本文中的说明将FTP帐户升级到SFTP并轮换SFTP密码。 分类导入器将被弃用，在&#x200B;**2026年8月31日**&#x200B;后无法再访问。 有关详细信息，请参阅[分类集概述](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview)。

## 先决条件

### Inventory your FTP accounts

You must complete the SFTP upgrade steps on this page for every FTP site used with Data Feeds or Data Warehouse.

因此，您必须确定正在接收数据馈送或Data Warehouse数据的所有FTP帐户。 此信息显示在FTP配置设置中，如[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md#configure-a-location-account)中的[旧帐户类型](/help/components/locations/configure-import-accounts.md)部分所述。

针对每个帐户，收集以下信息：

* **Host**: The hostname of the FTP server your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth).

* **Port**: When using an Adobe-hosted SFTP server, SFTP clients connect on port 22. FTP connections that are non-secure use port 21.

* **Username**: The username used to log in to the FTP server.

* **Location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface.

### 确认您可以在工具中更新凭据

Make sure you can update the SFTP passwords in whatever tool or script you use to connect to the SFTP site (for example, an SFTP client, automated script, or third-party platform).

All clients should connect via SFTP with password as a fallback.

## Upgrade FTP servers to use SFTP

>[!IMPORTANT]
>
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or analytics vendor), coordinate with them before following the steps in this article.

### Step 1: Generate your organization&#39;s SSH keys for downloading data

本节介绍如何生成组织的SSH密钥（公钥/私钥对），这些密钥用于从SFTP服务器&#x200B;**下载数据**。

>[!NOTE]
>
>在将来的步骤中，您将下载Adobe提供的另一个公钥。 这是第二个公钥/私钥对的一部分，Adobe使用该密钥对&#x200B;**将数据**&#x200B;上传到SFTP服务器。

要设置安全传输以从FTP服务器下载数据，请执行以下操作：

1. 登录到可从FTP服务器下载数据的工作站。

1. 生成公钥/私钥对以用于安全传输。

   When using an Adobe-hosted SFTP server, Adobe supports RSA and ed25519 keys.

   * **In a Linux environment**: Run the following command to generate the ed25519 key pair:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **In a Windows environment**: Use PuTTYgen.

1. 创建名为 [!DNL `authorized_keys`] 的文件（无扩展名）。

1. Copy the contents of the public key into the [!DNL `authorized_keys`] file.

1. In a future step, you will come back to this [!DNL `authorized_keys`] file to add Adobe&#39;s public key, which is used by Adobe to upload data to the SFTP server. Then you will add the [!DNL `authorized_keys`] file to the SFTP server.

### Step 2: Create a new SFTP location account in Adobe Analytics

Create a new SFTP location account to replace each existing FTP account.

When creating a new SFTP location account, you must use the same hostname and username that are used in the existing FTP account it is replacing.

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
   | [!UICONTROL **Hostname**] | 您的SFTP主机名（例如，`ftp.omniture.com`）。 |
   | [!UICONTROL **Port**] | The firewall port through which data will be sent. This is port 22 for Adobe-hosted SFTP connections. |
   | [!UICONTROL **Username**] | Your SFTP username. Use the same username that you used for your FTP account. |

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

1. Upload the [!DNL `authorized_keys`] file to your FTP server:

   1. Connect to the FTP server and log in with your username and password.
This can be an Adobe-hosted FTP server or your own FTP server.
   1. 创建一个 [!DNL .ssh] 目录（如果没有）。
   1. 将 [!DNL `authorized_keys`] 文件上传到 [!DNL .ssh] 目录。

1. 更新防火墙设置以允许来自SFTP服务器的入站连接。 使用Adobe托管的SFTP服务器时，请允许来自端口22上Adobe IP范围的入站连接。

1. Test the connection by logging in to the server using your SFTP client.

1. Repeat this process for each SFTP account that you created in the previous section, [Create the SFTP account](#create-the-sftp-account).

1. Continue with the following section, [Add a location within the account](#add-a-location-within-the-account).

#### Add a location within the account

1. On the [!UICONTROL **Locations**] tab, select [!UICONTROL **Add location**].

1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse.

1. In the [!UICONTROL **Location account**] field, select the account you just created.

1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the SFTP server. Folders in the path must already exist; otherwise, an error occurs. 例如，`/folder_name/folder_name`。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. Repeat this process for each SFTP account you created.

有关详细说明，请参阅[配置云导入和导出位置](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations)。

### Step 3: Edit Data Feeds and Data Warehouse requests to use the new SFTP destination

Update any existing scheduled Data Feeds and Data Warehouse requests that currently send data to FTP destinations to use the new SFTP destinations you created.

#### Edit Data Feeds

编辑配置了旧FTP目标的每个计划数据馈送，以使用新的SFTP目标：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

1. Locate the data feed that you want to edit. To locate a data feed, you can [filter and search the list of data feeds](#filter-and-search-the-list-of-data-feeds).

1. Select the data feed in the [!UICONTROL **Feed name**] column.

   The [!UICONTROL **Edit _feed_name_**] page is displayed.

1. In the [!UICONTROL **Destination**] section, in the [!UICONTROL **Account**] field, use the drop-down menu to select the new SFTP destination that you created.

1. In the [!UICONTROL **Location**] field, use the drop-down menu to select the location in the SFTP account.

1. 选择&#x200B;[!UICONTROL **保存**]。

For more detailed information, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Edit Data Warehouse requests

Edit each scheduled Data Warehouse request that is configured with the old FTP destination to use the new SFTP destination:

1. In Adobe Analytics, select [!UICONTROL **Tools**] > [!UICONTROL **Data Warehouse**].

1. 在Data Warehouse页面上，选择要编辑的请求。

   ![管理请求](assets/dw-manage-request.png)

1. 选择&#x200B;[!UICONTROL **编辑**]。

1. 选择&#x200B;[!UICONTROL **报告目标**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **帐户**]&#x200B;字段中，使用下拉菜单选择您创建的新SFTP目标。

1. In the [!UICONTROL **Location**] field, use the drop-down menu to select the location in the SFTP account.

1. Select [!UICONTROL **Save changes**].

For more detailed information, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Step 4: Update your firewall settings

If you haven&#39;t already, you need to update your firewall settings, as follows:

* **使用Adobe的FTP服务器时**：您需要更新防火墙设置以允许端口22上的&#x200B;**出站**&#x200B;连接。

* **When using your own FTP server**: You need to update your firewall settings to allow **inbound** connection on whatever port you are hosting the service, which is typically port 22.

You should also remove old FTP-specific rules, such as allowing inbound connections on port 21. (FTP uses port 21, plus a range of additional ports for data transfer. As a security best practice, you should eventually remove this unnecessary access through your firewall.)

### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly

After updating each existing Data Feed and Data Warehouse request to use the new SFTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected.

### 步骤6：在升级后的SFTP服务器上轮换密码

将FTP服务器升级到SFTP后，还必须轮换SFTP密码，如下节[轮换SFTP密码](#rotate-your-sftp-password)中所述。

## 轮换您的SFTP密码

如果基于密钥的身份验证失败，则SFTP密码将用作回退身份验证方法。

从FTP升级到SFTP后，请尽快轮换SFTP密码。 它应根据您的既定政策继续定期轮换。

1. 联系Adobe客户关怀团队并请求获取新密码。

1. 为每个SFTP帐户提供&#x200B;**主机名**&#x200B;和&#x200B;**用户名**。

   客户关怀团队将为每个FTP帐户生成一个新密码。

1. 更新用于连接到SFTP服务器的客户端中的密码。


