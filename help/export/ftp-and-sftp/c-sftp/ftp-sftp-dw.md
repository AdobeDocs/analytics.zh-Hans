---
description: Adobe支持将数据仓库请求导出到SFTP服务器。
keywords: ftp；sftp
seo-description: Adobe支持将数据仓库请求导出到SFTP服务器。
seo-title: 将数据仓库请求发送到SFTP服务器
solution: Analytics
title: 将数据仓库请求发送到SFTP服务器
uuid: 393634a1-0643-4d63-bb6 e-fb80 f1 ba76 c1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 将数据仓库请求发送到SFTP服务器

Adobe支持将数据仓库请求导出到SFTP服务器。

请确保已完成以下任务：

Adobe支持将数据仓库请求导出到SFTP服务器，前提是满足以下条件：

* [!DNL sftp://] 协议在主机字段中指定(例如， [!DNL sftp://ftp.example.com])，并且在请求数据仓库报告时使用端口22。

   You can also use the [!DNL sftp+norename://] option, as described below.

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

* 目标不是 [!DNL ftp.omniture.com]。Adobe 内部服务器之间的 sFTP 协议不受支持。
* 目标支持单因素 (PKI) 身份验证。在需要双因素身份验证的情况下，报告的传送将失败。请确保您的服务器未配置为尝试使用双因素身份验证。Adobe Analytics 要求在登录时只使用密钥而不使用任何其他内容。
* Adobe 支持 SSHv2 加密，并可回退到 SSHv1（仅 RSA 密钥）。

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. 让您组织内的一名受支持用户联系客户关怀，以获取 [!DNL authorized_keys] 文件。
1. After this file is obtained, log in to the FTP site under the same credentials that are used for the [!DNL Data Warehouse] request.
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure the request as desired, then click **[!UICONTROL Advanced Delivery Options]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. 在“文件夹”字段中输入要在其中置入文件的文件夹的名称。文件夹是必填项。
1. 输入在步骤 2 中使用的相同用户名和密码。
1. Click **[!UICONTROL Send]**.

sFTP PUT 命令会将具有 .part 扩展名的临时文件放入指定的目录中。上传完成后，该文件扩展名将被重命名为最终的扩展名，此后便可随时供您使用。

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. 当SFTP服务器自动上传文件时，如果SFTP服务器处理文件重命名，则在上传完成之前不可能处理文件。
