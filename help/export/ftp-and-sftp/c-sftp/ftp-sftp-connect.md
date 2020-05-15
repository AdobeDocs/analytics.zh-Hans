---
description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
keywords: ftp;sftp
title: 通过 SFTP 连接到 Adobe FTP 帐户
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 通过 SFTP 连接到 Adobe FTP 帐户

有关通过 Adobe FTP 服务器设置安全传输的说明。

1. 申请由 Adobe 托管的 FTP 帐户（50MB 配额）。
1. 创建 RSA 公钥/私钥。在 Linux 中，运行：

   ```
   ssh-keygen -t rsa
   ```

   如果您在 Windows 环境下，请使用 puttyGen 创建这些密钥。

1. 创建名为 [!DNL authorized_keys] 的文件（无扩展名）。
1. 将公钥的内容复制到 [!DNL authorized_keys] 中。
1. 将 [!DNL authorized_keys] 上传到 FTP 帐户：

   * 连接到 Adobe FTP 帐户。
   * 创建一个 [!DNL .ssh] 目录（如果没有）。
   * 将 [!DNL authorized_keys] 文件上传到 [!DNL .ssh] 目录。

1. 通过使用 SFTP 登录到 FTP 帐户来测试连接。

有关更多详细信息，请参阅[在无密码的情况下通过 SFTP 连接到 Adobe_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。
