---
description: Adobe FTP 政策会自动禁用连续 90 天保持闲置状态的 FTP 帐户的访问权限。
keywords: ftp；sftp
seo-description: Adobe FTP 政策会自动禁用连续 90 天保持闲置状态的 FTP 帐户的访问权限。
seo-title: 删除FTP数据和FTP帐户
solution: Analytics
title: 删除FTP数据和FTP帐户
uuid: 1cd3add-3561-492a-9ed4-aedbd3 d5 b257
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 删除FTP数据和FTP帐户

Adobe FTP 政策会自动禁用连续 90 天保持闲置状态的 FTP 帐户的访问权限。

在经过另外 90 天的宽限期之后，Adobe 会删除已禁用的 FTP 帐户（并永久删除这些帐户中存储的所有数据）。例如，一个连续 90 天保持闲置状态的 FTP 帐户（从 2012 年 7 月 5 日起至 2012 年 10 月 2 日）会在 2012 年 10 月 3 日被禁用。它随后会在 2013 年 1 月 2 日被完全删除。

不会在 2012 年 10 月 3 日之前禁用帐户，也不会在 2013 年 1 月 2 日之前删除帐户。

Adobe 还会永久删除活动帐户中连续 90 天都未被访问的旧数据。

这些政策对 2012 年 7 月 5 日之后的所有 FTP 帐户同样有效。

为了在这一过程中协助我们，并确保增强的 FTP 环境继续为我们的客户提供安全可靠的数据传输，我们要求客户做到以下事项：

* 在出站数据已被成功传输到您的内部环境之后，从 FTP 系统中删除此数据。Adobe 会识别并删除在 90 天后仍留存在系统中的任何文件。
* 当不再需要 FTP 帐户时通知 Adobe，以停用并删除它们。

