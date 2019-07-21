---
description: 只能使用SFTP连接和替代身份验证方法使用FTP帐户连接不带密码。这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。
keywords: ftp；sftp
seo-description: 只能使用SFTP连接和替代身份验证方法使用FTP帐户连接不带密码。这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。
seo-title: 无需口令，通过SFTP连接到Adobe
solution: Analytics
title: 无需口令，通过SFTP连接到Adobe
uuid: 88728309-50d2-450b-b0 e6-7dfec61 b5 dbc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 无需口令，通过SFTP连接到Adobe

只能使用SFTP连接和替代身份验证方法使用FTP帐户连接不带密码。这涉及一个由两个文件（一个位于 FTP 帐户上，另一个位于您的计算机中）构成的组，被称为公钥和私钥组合。

这种方式的安全性不亚于密码身份验证。它是另一种形式的身份验证，但无需用户每次键入密码。在使用正确的情况下，这些文件可让特定的计算机在无需指定密码的情况下登录。这需要在每台计算机上逐一设置。不使用这些密钥文件的所有其他连接仍需指定一个密码。

某些客户端需要SFTP(安全文件传输协议)才能传输敏感数据。SFTP连接比常规FTP连接更加安全，因为它允许加密数据通信。默认情况下，所有Adobe FTP帐户均为SFTP。通过使用在端口22上连接的SFTP客户端，可以打开SFTP连接，该客户端连接到端口22(不安全的普通FTP连接21)。

使用SFTP时，在特殊情况下，可以使用私钥连接到帐户而无需口令。此方法可让您的计算机使用密钥文件进行身份验证，而不使用常规的密码身份验证。这意味着只有具备私钥的计算机可在无密码的情况下连接。所有其他计算机/用户仍需使用密码身份验证（除非也在这些计算机上设置了私钥）。

**设置私钥并将其用于无密码身份验证**

1. FTP 帐户已创建 (Adobe)。

   一位 Adobe 代表可创建一个 FTP 帐户（如果没有）。联系您的 Adobe 客户经理或 Adobe 客户关怀以创建帐户。
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

   上传并测试公钥。Connect to the Adobe FTP account and create a [!DNL .ssh] directory, if it does not already exist. Upload the [!DNL authorized_keys] file to this [!DNL .ssh] directory. 这可通过多种不同的方式完成（命令行、图形 FTP 客户端，等等）。只需要具备创建目录并上传文件的权限即可。

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

