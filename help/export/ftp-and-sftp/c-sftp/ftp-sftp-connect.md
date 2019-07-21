---
description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
keywords: ftp；sftp
seo-description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
seo-title: 使用SFTP连接到Adobe FTP帐户
solution: Analytics
title: 使用SFTP连接到Adobe FTP帐户
uuid: faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用SFTP连接到Adobe FTP帐户

有关通过 Adobe FTP 服务器设置安全传输的说明。

1. 申请由 Adobe 托管的 FTP 帐户（50MB 配额）。
1. 创建 RSA 公钥/私钥。在 Linux 中，运行：

   ```
   ssh-keygen -t rsa
   ```

   如果您在 Windows 环境下，请使用 puttyGen 创建这些密钥。

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * 连接到 Adobe FTP 帐户。
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. 使用SFTP登录FTP帐户，测试连接。

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
