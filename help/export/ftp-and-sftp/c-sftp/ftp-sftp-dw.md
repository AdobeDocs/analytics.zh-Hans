---
description: Adobe 支持将 Data Warehouse 请求导出至 SFTP 服务器。
keywords: ftp;sftp
title: 将 Data Warehouse 请求发送到 SFTP 服务器
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%

---

# 将 Data Warehouse 请求发送到 SFTP 服务器

Adobe支持将Data Warehouse请求导出到SFTP服务器，如[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)一文中的[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp)中所述。

请确保已完成以下任务：

* 请求Data Warehouse报告时仅使用端口22。
* Adobe的`authorized_keys`文件位于您登录的用户根目录中的`.ssh`目录中。
* 目标不是 `ftp.omniture.com`。Adobe 内部服务器之间的 sFTP 协议不受支持。
* 目标支持单因素 (PKI) 身份验证。在需要双因素身份验证的情况下，报告的传送将失败。请确保您的服务器未配置为尝试使用双重身份验证。 Adobe Analytics 要求在登录时只使用密钥而不使用任何其他内容。
* Adobe 支持 SSHv2 加密，并可回退到 SSHv1（仅 RSA 密钥）。

要通过 SFTP 成功地发送 Data Warehouse 请求，请执行以下操作：

1. 完成[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) [为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)一文中所述的步骤，包括下载公钥。
1. 使用与Data Warehouse请求相同的凭据登录到SFTP站点。
1. 在根目录中，导航到名为 `.ssh` 的文件夹（如果不存在，请创建一个），并将 `authorized_keys` 文件置于此处。

1. 如果尚未完成Data Warehouse请求，请按照[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中的说明完成请求。
