---
description: 设置并使用 Adobe 托管的 FTP 帐户。
keywords: ftp；sftp
seo-description: 设置并使用 Adobe 托管的 FTP 帐户。
seo-title: 设置FTP帐户-概述
solution: Analytics
title: 设置FTP帐户-概述
uuid: e5524619-248a-4aae-9f64-cd7 d33 f3 c407
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 设置FTP帐户-概述

设置并使用 Adobe 托管的 FTP 帐户。

Adobe 维护有具备高可用性和性能的 FTP 群集，这些群集专门用来改进文件传输的可靠性，同时又能继续确保高性能。

Adobe 客户会通过标准流程收到有关维护事件计划的通知。为了确保 Adobe FTP 系统正常工作并继续提供安全可靠的高性能数据传输，Adobe 要求遵守以下准则：

* 大多数 Adobe FTP 帐户（分类、数据源及其他）在设置了既定功能的情况下会自动启用。对于数据馈送和常规文件传送帐户，Adobe 客户关怀可为您设置一个新的 FTP 帐户。使用此流程可确保 FTP 帐户的安全性和可用空间。
* 在 Adobe 传送到 FTP 帐户的数据已被成功传输到系统之后，用户应当删除这些数据。
* 请在不再需要 FTP 帐户时通知 Adobe，以停用它们。

The Adobe FTP host name is [!DNL ftp.omniture.com] or [!DNL ftp2.omniture.com].

This information, along with a username and password, should be provided either within the [!UICONTROL Experience Cloud] (for classifications and Data Sources), or by the Adobe representative responsible for setting up the account at your request. 如果您不知道要使用哪个 FTP 地址，请联系您的 Adobe 客户经理，他可为您提供正确的地址。此外，对于分类和数据源帐户，Adobe 不确定会在一天中的哪个具体时段处理 FTP 文件。Adobe 会使用一个可持续轮询 FTP 帐户的脚本，来用于新文件的处理。已上传到这些帐户的文件将得到尽快的处理。
