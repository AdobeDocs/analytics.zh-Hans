---
description: 设置和使用 Adobe 托管的 FTP 帐户。
keywords: ftp;sftp
title: 设置 FTP 帐户 — 概述
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
source-git-commit: 6008cd51b86e403668c15bbfb9d50513e46ddf4d
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 17%

---

# 设置FTP或SFTP帐户 — 概述

设置并使用Adobe托管的FTP或SFTP帐户。

Adobe维护高可用高性能FTP或SFTP群集，这些群集专门用于提高文件传输可靠性，同时继续确保高性能。

Adobe客户会通过其标准流程接收维护通知，因为维护事件会按计划进行。 为了确保Adobe FTP或SFTP系统按设计运行并持续提供安全可靠的高性能数据传输，Adobe请遵循以下准则：

* 设置给定功能后，大多数Adobe FTP或SFTP帐户（分类、数据源等）都会自动启用。 对于数据馈送和常规文件投放帐户，Adobe客户关怀团队可以为您设置新的FTP或SFTP帐户。 此过程旨在确保FTP或SFTP帐户的安全性和可用空间。
* 成功将Adobe传送到FTP或SFTP帐户的数据传输到用户系统后，用户应将这些数据移除。
* 当不再需要FTP或SFTP帐户时通知Adobe，以便可以停用它们。

Adobe FTP 主机名为 `ftp://ftp.omniture.com` 或 `ftp://ftp2.omniture.com`。

该信息连同用户名和密码，应当在 [!UICONTROL Experience Cloud]（对于分类和数据源）中提供，或由负责按照您的请求设置帐户的 Adobe 代表提供。如果您不知道要使用哪个FTP或SFTP地址，请联系您的Adobe客户团队，他们可以提供正确的地址。 此外，对于分类帐户和数据源帐户，Adobe没有一天中用于处理FTP或SFTP文件的特定时间。 相反，Adobe使用不断轮询FTP或SFTP帐户以查找新文件流程的脚本。 系统会尽快处理上载到这些帐户中的文件。
