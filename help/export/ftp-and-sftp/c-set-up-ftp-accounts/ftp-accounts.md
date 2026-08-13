---
description: 设置和使用 Adobe 托管的 FTP 帐户。
keywords: ftp;sftp
title: 设置 FTP 帐户 — 概述
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: 'https://experienceleague.adobe.com/dB-Sb1aM5VYz5FAkvxOunFGeAQvttU7vxCjjqj1pesQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 6%

---

# 设置FTP或SFTP帐户 — 概述

设置并使用Adobe托管的FTP或SFTP帐户。

Adobe维护高可用高性能FTP或SFTP群集，这些群集专门用于提高文件传输可靠性，同时继续确保高性能。

Adobe客户会通过其标准流程接收维护通知，因为维护事件会按计划进行。 为了确保Adobe FTP或SFTP系统按设计运行并持续提供安全可靠的高性能数据传输，Adobe请遵循以下准则：

* 设置给定功能后，大多数Adobe FTP或SFTP帐户（分类、数据源等）都会自动启用。 对于数据馈送和常规文件投放帐户，Adobe客户关怀团队可以为您设置新的FTP或SFTP帐户。 此过程旨在确保FTP或SFTP帐户的安全性和可用空间。
* 成功将Adobe传送到FTP或SFTP帐户的数据传输到用户系统后，用户应将这些数据移除。
* 当不再需要FTP或SFTP帐户时通知Adobe，以便可以停用它们。

Adobe FTP 主机名为 `ftp://ftp.omniture.com` 或 `ftp://ftp2.omniture.com`。

此信息连同用户名和密码，应当在CX Enterprise中（对于分类和数据源）提供，或由负责按照您的请求设置帐户的Adobe代表提供。 如果您不知道要使用哪个FTP或SFTP地址，请联系您的Adobe客户团队，他们可以提供正确的地址。 此外，对于分类帐户和数据源帐户，Adobe没有一天中用于处理FTP或SFTP文件的特定时间。 相反，Adobe使用不断轮询FTP或SFTP帐户以查找新文件流程的脚本。 系统会尽快处理上载到这些帐户中的文件。
