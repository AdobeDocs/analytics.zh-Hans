---
description: 数据馈送是 Adobe 收到的 Clickstream 数据的导出格式，可提供标准和自定义的数据馈送。
keywords: ftp;sftp
title: 数据馈送
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# 数据馈送

数据馈送是 Adobe 收到的 Clickstream 数据的导出格式，可提供标准和自定义的[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已购买Adobe Data Warehouse、 [!UICONTROL Standard Data Feeds] ，则可以设置您自己的Analytics数据馈送。 可将它们发送到任何 FTP 帐户（无论是由 Adobe 设置的帐户还是外部 FTP）。Adobe 工程技术服务提供了几乎可通过任何方式发送的自定义[!UICONTROL 数据馈送]。

[!UICONTROL 数据]源FTP帐户允许10GB（默认）。 所有其他标准 FTP 帐户的默认限制为 50MB。在客户端将 FTP 帐户用于适当用途的情况下，某些高流量用户可快速填满这些帐户。当 FPT 帐户已填满时，不可再向其推送任何其他文件。因此，传送给该 FTP 帐户的任何文件（[!UICONTROL 数据馈送]、数据仓库请求等）都不会被传送。正因如此，通过删除已接收和下载的文件来管理 Adobe FTP 帐户才会如此重要。

当 FTP 帐户已填满时，您应当下载并删除当前的文件，并让 Adobe 知道空间已清理。Adobe 随后可以重新发送还未传送的文件。某些工具，如数据仓库，允许用户重新发送这些文件。重新发送可能不需要 Adobe 的介入。如果您的 FTP 帐户总是频繁被填满，请联系 Adobe 客户关怀，他们会建议您采用其他传送选项，以增加帐户上的 FTP 空间和文件数量配额。
