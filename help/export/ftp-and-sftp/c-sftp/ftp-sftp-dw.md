---
description: Adobe 支持将 Data Warehouse 请求导出至 SFTP 服务器。
keywords: ftp;sftp
title: 将 Data Warehouse 请求发送到 SFTP 服务器
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: 'https://experienceleague.adobe.com/gZvqhVFN2WKnk0hs2t8R5fcg5g8Tts1jKZPvMqeGcy4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 31%

---

# 将 Data Warehouse 请求发送到 SFTP 服务器

Adobe支持将Data Warehouse请求导出到SFTP服务器，如[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)一文中的[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp)中所述。

请确保已完成以下任务：

* 请求Data Warehouse报告时仅使用端口22。
* Adobe的`authorized_keys`文件位于您登录的用户根目录中的`.ssh`目录中。
* 目标不是 `ftp.omniture.com`。 不支持Adobe内部服务器之间的SFTP协议。
* 目标支持单因素(PKI)身份验证。 如果存在双重因素挑战，则报表交付将会失败。 请确保您的服务器未配置为尝试使用双重身份验证。 Adobe Analytics要求登录时只使用密钥，而不使用其他任何方法。
* Adobe支持SSHv2加密，并回退到SSHv1（仅限RSA密钥）。

要通过 SFTP 成功地发送 Data Warehouse 请求，请执行以下操作：

1. 完成文章[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp)所述的步骤，包括下载公钥。
1. 使用与Data Warehouse请求相同的凭据登录到SFTP站点。
1. 在根目录中，导航到名为 `.ssh` 的文件夹（如果不存在，请创建一个），并将 `authorized_keys` 文件置于此处。

1. 如果您尚未完成Data Warehouse请求，请按照[为Data Warehouse请求配置报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)中的说明完成此操作。
