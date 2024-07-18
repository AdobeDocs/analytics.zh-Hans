---
description: 只有在同时使用 SFTP 连接和另一种身份验证方法时，才可以在无密码的情况下连接至 FTP 帐户。这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。
keywords: ftp;sftp
title: 在无密码的情况下通过 SFTP 连接到 Adobe
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 97%

---

# 在无密码的情况下通过 SFTP 连接到 Adobe

只有在同时使用 SFTP 连接和另一种身份验证方法时，才可以在无密码的情况下连接至 FTP 帐户。这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。

这种方式的安全性不亚于密码身份验证。它是另一种形式的身份验证，但无需用户每次键入密码。在使用正确的情况下，这些文件可让特定的计算机在无需指定密码的情况下登录。这需要在每台计算机上逐一设置。不使用这些密钥文件的所有其他连接仍需指定一个密码。

某些客户端在传输敏感数据时需要使用 SFTP（安全文件传输协议）。SFTP 连接比常规的 FTP 连接更加安全，因为它允许经过加密的数据通信。默认情况下，所有 Adobe FTP 帐户均可使用 SFTP。使用连接到端口 22 的 SFTP 客户端（常规的非安全 FTP 连接使用端口 21），并提供一个有效的用户名和密码可打开 SFTP 连接。

在使用 SFTP 时，可在特定的条件下使用私钥连接到帐户，而无需密码。此方法可让您的计算机使用密钥文件进行身份验证，而不使用常规的密码身份验证。这意味着只有具备私钥的计算机可在无密码的情况下连接。所有其他计算机/用户仍需使用密码身份验证（除非也在这些计算机上设置了私钥）。

**设置私钥并将其用于无密码身份验证**

1. FTP 帐户已创建 (Adobe)。

   一位 Adobe 代表可创建一个 FTP 帐户（如果没有）。请联系您的Adobe客户团队或Adobe客户关怀团队以创建帐户。
1. 公钥/私钥创建（客户）。

   创建公钥和私钥组合。私钥是您的计算机/服务器上私有的文件，并会留存在那里。公钥文件需要上传到 Adobe 帐户。在通过这种方式使用时，您无需密码身份验证即可连接。位于 Adobe 的公钥文件匹配您的计算机/服务器上的私钥文件，并以该方式进行身份验证。

   要创建这些文件，请设置您的内部网络以支持组参与，创建一个适用于您的环境的密钥集。有很多工具和应用程序可用于创建这两个文件。

   下面是一个有关如何在 UNIX shell 环境下完成此项操作的示例。这只是一个操作示例，可作为参考与您的团队或内部网络组沟通相关要求。

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

1. 将公钥上传到 FTP 帐户（客户）。

   上传并测试公钥。连接到 Adobe FTP 帐户并创建一个 [!DNL .ssh] 目录（如果没有）。将 [!DNL authorized_keys] 文件上传到此 [!DNL .ssh] 目录。这可通过多种不同的方式完成（命令行、图形 FTP 客户端，等等）。只需要具备创建目录并上传文件的权限即可。

   这里也是一个使用 Unix shell 执行此操作的示例。

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
