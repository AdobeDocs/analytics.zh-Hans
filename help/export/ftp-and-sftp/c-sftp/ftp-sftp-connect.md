---
description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
keywords: ftp;sftp
seo-description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
seo-title: 通过 SFTP 连接到 Adobe FTP 帐户
solution: Analytics
title: 通过 SFTP 连接到 Adobe FTP 帐户
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 通过 SFTP 连接到 Adobe FTP 帐户

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

1. 使用SFTP登录到FTP帐户，以测试连接。

[有关详细信息，请参 ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)阅如何通过sFTP无口令连接到Adobe_....
