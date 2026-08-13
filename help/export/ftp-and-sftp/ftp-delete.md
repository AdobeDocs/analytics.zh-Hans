---
description: Adobe FTP 政策会自动禁用连续 90 天保持闲置状态的 FTP 帐户的访问权限。
keywords: ftp;sftp
title: 删除FTP和SFTP帐户和数据
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: 'https://experienceleague.adobe.com/i2jpzTOx-CJzWjHMXT14EE761uGvNjcoW3f1dyF0ZlA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 8%

---

# 删除FTP和SFTP帐户和数据

Adobe FTP和SFTP策略可能会禁用对连续90天保持闲置状态的FTP和SFTP帐户的访问。

在额外的90天宽限期后，Adobe可能会删除已禁用的FTP和SFTP帐户（并永久删除这些帐户中存储的所有数据）。 例如，闲置90天（从2025年7月5日至2025年10月2日）的SFTP帐户已于2025年10月3日禁用。 然后，它于2026年1月2日被完全删除。

在2025年10月5日之前没有账户被禁用，在2026年1月2日之前没有账户被删除。

如果90天未访问活动帐户中的旧数据，Adobe也可以永久删除该数据。

为了在此过程中协助我们并确保FTP或SFTP环境继续为客户提供安全可靠的数据传输，我们要求客户执行以下操作：

* 成功将传出数据传输到内部环境后，从FTP和SFTP系统中删除该数据。 Adobe可能会在90天后识别并删除系统中剩余的任何文件。
* 当不再需要FTP和SFTP帐户时通知Adobe，以便可以停用和删除这些帐户。
