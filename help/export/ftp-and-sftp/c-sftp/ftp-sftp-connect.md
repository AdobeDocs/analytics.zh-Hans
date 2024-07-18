---
description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
keywords: ftp;sftp
title: 通过 SFTP 连接到 Adobe FTP 帐户
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 58%

---

# 通过SFTP连接到FTP帐户

要通过FTP设置安全传输，请执行以下操作：

1. （视情况而定）如果要设置与AdobeFTP服务器的安全传输：

   1. 申请由 Adobe 托管的 FTP 帐户（50MB 配额）。

   1. 创建公共/私有RSA密钥。

      * 在Linux环境中，运行：

        ```
        ssh-keygen -t rsa
        ```

      * 在Windows环境中，使用puttyGen。

1. （视情况而定）如果要使用自己的FTP位置设置安全传输，则必须具有包含有效RSA或DSA公钥的SFTP主机、用户名和目的地站点。 您可以在创建馈送时下载相应的公钥。

1. 创建名为 [!DNL authorized_keys] 的文件（无扩展名）。

1. 将公钥的内容复制到 [!DNL authorized_keys] 中。

1. 将 [!DNL authorized_keys] 上传到 FTP 帐户：

   * 连接到 Adobe FTP 帐户。
   * 创建一个 [!DNL .ssh] 目录（如果没有）。
   * 将 [!DNL authorized_keys] 文件上传到 [!DNL .ssh] 目录。

1. 通过使用 SFTP 登录到 FTP 帐户来测试连接。

有关更多详细信息，请参阅[在无密码的情况下通过 SFTP 连接到 Adobe_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。
