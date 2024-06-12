---
description: 升级 Adobe FTP 服务器可能会引入影响（一般用于定期下载或上传数据的）自动化脚本的新配置，而这些脚本往往构建得依赖某些服务器设置。
keywords: ftp;sftp
title: 升级 Adobe FTP 服务器
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# 升级 Adobe FTP 服务器

升级 Adobe FTP 服务器可能会引入影响（一般用于定期下载或上传数据的）自动化脚本的新配置，而这些脚本往往构建得依赖某些服务器设置。

例如，引入一个新的成功状态时，它会影响使用该成功状态来触发特定操作的脚本。Adobe 会主动向用户通知这类配置更改。如果 Adobe 通知您某项 FTP 服务器升级即将进行，请检查您的自动脚本以确保它们仍能正常工作。
