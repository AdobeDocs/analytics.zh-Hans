---
description: 有关通过 Adobe FTP 服务器设置安全传输的说明。
keywords: ftp;sftp
title: 通过 SFTP 连接到 Adobe FTP 帐户
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: https://experienceleague.adobe.com/uXtJtDP58tSIzb9AvoAknAYoMt7SknJSgxRKNgIAXM8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 38%

---

# 通过SFTP连接到FTP帐户

要通过FTP设置安全传输，请执行以下操作：

1. （视情况而定）如果您要设置与Adobe FTP服务器的安全传输：

   1. 请求Adobe托管的FTP帐户（50 MB配额）。

   1. 创建公钥/私钥。

      * 在Linux环境中，运行：

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        如果您的策略不允许您使用ed25519，请运行：

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **注意：**&#x200B;这通常适用于在FIPS 186-4下运行的客户，如ed25519，新版FIPS 186-5首先支持这些客户。

      * 在Windows环境中，使用puttyGen。

1. （视情况而定）如果要使用自己的FTP位置设置安全传输，则必须具有包含有效RSA或ed25519公钥的SFTP主机、用户名和目的地站点。 您可以在创建馈送时下载相应的公钥。

1. 创建名为 [!DNL `authorized_keys`] 的文件（无扩展名）。

1. 将公钥的内容复制到 [!DNL `authorized_keys`] 中。

1. 将 [!DNL `authorized_keys`] 上传到 FTP 帐户：

   * 连接到 Adobe FTP 帐户。
   * 创建一个 [!DNL .ssh] 目录（如果没有）。
   * 将 [!DNL `authorized_keys`] 文件上传到 [!DNL .ssh] 目录。

1. 通过使用 SFTP 登录到 FTP 帐户来测试连接。

有关详细信息，请参阅[在无密码的情况下通过SFTP连接到Adobe](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)。

