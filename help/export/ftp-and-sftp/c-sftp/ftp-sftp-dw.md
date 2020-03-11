---
description: Adobe 支持将 Data Warehouse 请求导出至 SFTP 服务器。
keywords: ftp;sftp
title: 将 Data Warehouse 请求发送到 SFTP 服务器
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 将 Data Warehouse 请求发送到 SFTP 服务器

Adobe 支持将 Data Warehouse 请求导出至 SFTP 服务器。

请确保已完成以下任务：

在满足以下要求时，Adobe 支持将 Data Warehouse 请求导出到 SFTP 服务器：

* [!DNL sftp://] 协议在主机字段中指定（例如，[!DNL sftp://ftp.example.com]），且在请求 Data Warehouse 报表时仅使用端口 22。

   此外，您还可以使用如下所述的 [!DNL sftp+norename://] 选项。

* Adobe 的 [!DNL authorized_keys] 文件位于您登录的用户根目录内的 [!DNL .ssh] 目录中。

* 目标不是 [!DNL ftp.omniture.com]。Adobe 内部服务器之间的 sFTP 协议不受支持。
* 目标支持单因素 (PKI) 身份验证。在需要双因素身份验证的情况下，报告的传送将失败。请确保您的服务器未配置为尝试使用双因素身份验证。Adobe Analytics 要求在登录时只使用密钥而不使用任何其他内容。
* Adobe 支持 SSHv2 加密，并可回退到 SSHv1（仅 RSA 密钥）。

要通过 SFTP 成功地发送 [!DNL Data Warehouse] 请求，请执行以下操作：

1. 让您组织内的一名受支持用户联系客户关怀，以获取 [!DNL authorized_keys] 文件。
1. 在获取此文件后，使用与 [!DNL Data Warehouse] 请求相同的凭据登录到 FTP 站点。
1. 在根目录中，导航到名为 [!DNL .ssh] 的文件夹（如果不存在，请创建一个），并将 [!DNL authorized_keys] 文件置于此处。

1. 转到 [!DNL Data Warehouse] 请求管理器。按需要配置请求，然后单击&#x200B;**[!UICONTROL 高级传送选项]**。

1. 在弹出窗口中，单击 **[!UICONTROL FTP]**，然后指定通过端口 22 连接的 FTP 站点（包括 [!DNL sftp://] 协议，例如 [!DNL sftp://ftp.omniture.com]）。

   仅在使用 SFTP 时才允许包含 [!DNL sftp://] 协议。常规 FTP 请求应当忽略协议前缀（例如 [!DNL ftp.omniture.com]，而不是 [!DNL ftp://ftp.omniture.com]）。

1. 在“文件夹”字段中输入要在其中置入文件的文件夹的名称。文件夹是必填项。
1. 输入在步骤 2 中使用的相同用户名和密码。
1. 单击&#x200B;**[!UICONTROL 发送]**。

sFTP PUT 命令会将具有 .part 扩展名的临时文件放入指定的目录中。上传完成后，该文件扩展名将被重命名为最终的扩展名，此后便可随时供您使用。

此外，可以指定 [!DNL sftp+norename://] 而不是 [!DNL sftp://]，以直接使用最终名称上传文件，而不会在上传期间使用临时的 [!DNL .part] 文件名。当 SFTP 服务器在上传期间自动处理文件重命名时，且在上传完成之前不可能处理文件，此方法较为合适。
