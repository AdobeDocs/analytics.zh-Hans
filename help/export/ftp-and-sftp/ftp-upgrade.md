---
description: 升级 Adobe FTP 服务器会引入一些新配置并对自动脚本（通常用于定期下载或上传数据）产生影响，且这些脚本的构建通常依赖于特定的服务器设置。
keywords: ftp;sftp
solution: Analytics
title: 升级 Adobe FTP 服务器
uuid: cc9e5e13-e213-480f-9ff6-3dbec24baeee
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 升级 Adobe FTP 服务器

升级 Adobe FTP 服务器会引入一些新配置并对自动脚本（通常用于定期下载或上传数据）产生影响，且这些脚本的构建通常依赖于特定的服务器设置。

例如，引入一个新的成功状态时，它会影响使用该成功状态来触发特定操作的脚本。Adobe 会主动向用户通知这类配置更改。如果 Adobe 通知您某项 FTP 服务器升级即将进行，请检查您的自动脚本以确保它们仍能正常工作。
