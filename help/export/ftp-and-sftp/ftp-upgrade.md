---
description: 升级 Adobe FTP 服务器可能会引入影响（一般用于定期下载或上传数据的）自动化脚本的新配置，而这些脚本往往构建得依赖某些服务器设置。
keywords: ftp;sftp
title: 升级Adobe FTP和SFTP服务器
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: 'https://experienceleague.adobe.com/RJHgVwgnmCLRuNTyjKx-D6SlOovFYS0T5-7topZkcVY'
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
source-wordcount: 131
ht-degree: 25%

---

# 升级Adobe FTP和SFTP服务器

升级Adobe FTP和SFTP服务器会引入一些新配置，这些配置会影响自动化脚本（通常用于定期下载或上传数据），而这些脚本的构建通常依赖于某些服务器设置。

例如，引入了新的成功状态，这会影响使用成功状态触发特定操作的脚本。 Adobe会主动通知用户此类配置更改。 如果Adobe通知您即将升级FTP服务器，请检查您的自动化脚本，确保它们仍然正常运行。
