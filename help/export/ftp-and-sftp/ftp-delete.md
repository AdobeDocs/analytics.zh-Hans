---
description: Adobe FTP 政策会自动禁用连续 90 天保持闲置状态的 FTP 帐户的访问权限。
keywords: ftp;sftp
title: 删除FTP和SFTP帐户和数据
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '223'
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
