---
description: 只有在同时使用 SFTP 连接和另一种身份验证方法时，才可以在无密码的情况下连接至 FTP 帐户。 这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。
keywords: ftp;sftp
title: 在无密码的情况下通过 SFTP 连接到 Adobe
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
TQID: 'https://experienceleague.adobe.com/5XpefTP6xLr007yTQjLDVoj-j-EcPLvBDda-NNIg6xA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 38%

---

# 在无密码的情况下通过 SFTP 连接到 Adobe

只有在同时使用 SFTP 连接和另一种身份验证方法时，才可以在无密码的情况下连接至 FTP 帐户。 这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。

这与密码身份验证同样安全。 它是另一种身份验证形式，不需要用户每次都键入密码。 正确使用这些文件后，该特定计算机无需指定密码即可登录。 这需要逐台计算机进行设置。 所有其他不使用这些密钥文件的连接仍需要指定密码。

某些客户端在传输敏感数据时需要使用 SFTP（安全文件传输协议）。 SFTP 连接比常规的 FTP 连接更加安全，因为它允许经过加密的数据通信。 默认情况下，所有 Adobe FTP 帐户均可使用 SFTP。 使用连接到端口 22 的 SFTP 客户端（常规的非安全 FTP 连接使用端口 21），并提供一个有效的用户名和密码可打开 SFTP 连接。

在使用 SFTP 时，可在特定的条件下使用私钥连接到帐户，而无需密码。 此方法允许计算机使用密钥文件进行身份验证，而不是使用通常的密码身份验证。 这意味着，只有持有私钥的计算机可以在没有密码的情况下连接。 所有其他计算机/用户仍需要使用密码身份验证（除非在这些其他计算机上也设置了私钥）。

**要设置和使用私钥进行无密码身份验证**

1. 已创建FTP帐户(Adobe)。

   Adobe代表可以创建FTP帐户（如果尚不存在）。 请联系您的Adobe客户团队或Adobe客户关怀团队以创建帐户。
1. 公钥/私钥创建（客户）。

   创建公钥和私钥组合。 私钥是计算机/服务器的私有文件，它驻留在计算机上。 需要将该公钥文件上传到Adobe帐户。 以这种方式使用时，无需密码验证即可连接。 Adobe中的公钥文件与您的计算机/服务器上的私钥文件匹配，并以该方式进行身份验证。

   要创建这些文件，请让您的内部网络支持小组创建一个适合您环境的密钥集。 有许多工具和应用程序可用于创建这两个文件。

   下面显示了如何在UNIX Shell环境中执行此操作的示例。 这只是如何执行此操作的其中一个示例，并作为向团队或内部网络组传达要求的有用参考点。

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. 将公钥上传到FTP帐户（客户）。

   上载并测试公钥。 连接到 Adobe FTP 帐户并创建一个 [!DNL .ssh] 目录（如果没有）。 将 [!DNL authorized_keys] 文件上传到此 [!DNL .ssh] 目录。 这可以通过多种不同的方式（命令行、图形FTP客户端等）实现。 只需创建目录和上传文件即可。

   这里，再次是使用UNIX shell执行此操作的示例。

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
