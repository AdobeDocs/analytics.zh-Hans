---
title: FTP和SFTP服务器的安全要求
description: 了解FTP和SFTP服务器的安全要求。
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 2%

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
>* **Adobe建议尽可能转换到新版云目标，而不是升级到SFTP。**
>FTP和SFTP是旧版目标类型。 Adobe建议迁移到现代云目标类型（例如Amazon S3、Google Cloud Platform或Azure），而不是像本文所述将FTP帐户升级到SFTP和轮换SFTP密码。 这些云目标提供了更高级别的安全性。 有关详细信息，请参阅[配置云导入和导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts)。
>
>* **如果FTP和SFTP帐户专门用于分类，请迁移到分类集。**
>如果您的FTP或SFTP帐户专门用于分类，则您应该从&#x200B;**分类导入器**&#x200B;迁移到&#x200B;**分类集**，而不是按照本文中的说明将FTP帐户升级到SFTP并轮换SFTP密码。 分类导入器将被弃用，在&#x200B;**2026年8月31日**&#x200B;后无法再访问。 有关详细信息，请参阅[分类集概述](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/classifications/sets/overview)。

## 先决条件

### 清点FTP帐户

对于用于数据馈送和Data Warehouse的每个FTP站点，必须完成此页面上描述的将FTP服务器升级为使用SFTP的过程。

因此，您必须识别所有接收数据馈送或Data Warehouse数据的FTP帐户。 此信息显示在FTP配置设置中，如[配置云导入和导出帐户](/help/components/locations/configure-import-accounts.md#configure-a-location-account)中的[旧帐户类型](/help/components/locations/configure-import-accounts.md)部分所述。

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

   使用Adobe托管的FTP服务器时，Adobe支持RSA和ed25519密钥。

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

1. 在&#x200B;[!UICONTROL **帐户类型**]&#x200B;下拉字段中，选择&#x200B;[!UICONTROL **SFTP（旧版）**]。

1. 请完成以下字段：

   | 字段名称 | 功能 |
   |---------|----------|
   | [!UICONTROL **主机名**] | 您的SFTP主机名（例如，`ftp.omniture.com`）。 |
   | [!UICONTROL **端口**] | 用于发送数据的防火墙端口。 这是Adobe托管的SFTP连接的端口22。 |
   | [!UICONTROL **用户名**] | SFTP用户名。 使用与您的FTP帐户相同的用户名。 |

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 在&#x200B;[!UICONTROL **创建的帐户**]&#x200B;对话框中，下载RSA或ed25519公钥，然后选择&#x200B;**[!UICONTROL 确定]**。 这是Adobe用于将数据上传到SFTP服务器的SSH公钥。 （在以下部分[将Adobe的SSH公钥添加到SFTP服务器](#add-adobes-ssh-public-key-to-the-sftp-server)中使用此密钥。）

1. 对要创建的每个SFTP帐户重复此过程。

1. 继续下面的部分，[将公钥上传到SFTP服务器](#upload-the-public-key-to-the-sftp-server)。

#### 将Adobe的SSH公钥添加到`authorized_keys`文件并将其上传到FTP服务器

您在上一节的步骤7中下载的公钥是Adobe用于&#x200B;**将数据上传**&#x200B;到SFTP服务器的公钥/私钥对的一部分。

您需要将此公钥添加到您之前在其中添加您组织的下载密钥的`authorized_keys`文件中（您在[步骤1：生成您组织的下载密钥并将其添加到FTP服务器](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)）。

要将Adobe的SSH公钥添加到`authorized_keys`文件并将其上载到FTP服务器，请执行以下操作：

1. 登录到可从FTP服务器下载数据的工作站。

1. 打开[!DNL `authorized_keys`]文件并添加Adobe的上传密钥。 此文件应已包含贵组织的下载密钥（从[开始）步骤1：生成贵组织的下载密钥，并将其添加到您的FTP服务器](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)。

1. 将[!DNL `authorized_keys`]文件上传到FTP服务器：

   1. 连接到FTP服务器并使用您的用户名和密码登录。\
      这可以是由Adobe托管的FTP服务器或您自己的FTP服务器。
   1. 创建一个 [!DNL .ssh] 目录（如果没有）。
   1. 将 [!DNL `authorized_keys`] 文件上传到 [!DNL .ssh] 目录。

1. 更新防火墙设置以允许来自SFTP服务器的入站连接。 使用Adobe托管的SFTP服务器时，请允许来自端口22上Adobe IP范围的入站连接。

1. 通过使用SFTP客户端登录到服务器来测试连接。

1. 对您在上一节[创建SFTP帐户](#create-the-sftp-account)中创建的每个SFTP帐户重复此过程。

1. 继续下面的部分，[在帐户](#add-a-location-within-the-account)中添加位置。

#### 在帐户中添加位置

1. 在&#x200B;**位置**&#x200B;选项卡上，选择&#x200B;**添加位置**。

1. 指定名称、描述，以及此位置是将与数据馈送还是Data Warehouse一起使用。

1. 在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中，选择您刚刚创建的帐户。

1. 在&#x200B;[!UICONTROL **目录路径**]&#x200B;字段中，指定SFTP服务器上目录的路径。 路径中的文件夹必须已存在；否则，会发生错误。 例如，`/folder_name/folder_name`。

1. 选择&#x200B;**保存**。

1. 为您创建的每个SFTP帐户重复此过程。

有关详细说明，请参阅[配置云导入和导出位置](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations)。

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

有关详细信息，请参阅[管理数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed)中的[编辑数据馈送](/help/export/analytics-data-feed/df-manage-feeds.md)。

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

有关详细信息，请参阅[管理Data Warehouse请求](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests)中的[编辑请求](/help/export/data-warehouse/data-warehouse-requests-manage.md)。

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


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

