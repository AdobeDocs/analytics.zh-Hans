---
description: 数据馈送是 Adobe 收到的 Clickstream 数据的导出格式，可提供标准和自定义的数据馈送。
keywords: ftp；sftp
seo-description: 数据馈送是 Adobe 收到的 Clickstream 数据的导出格式，可提供标准和自定义的数据馈送。
seo-title: 数据馈送
solution: Analytics
title: 数据馈送
uuid: 3c70eea3-ca59-4aa5-64e1 bb677 bfa677 bfa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 数据馈送

数据馈送是 Adobe 收到的 Clickstream 数据的导出格式，可提供标准和自定义的[数据馈送](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md)。

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. 可将它们发送到任何 FTP 帐户（无论是由 Adobe 设置的帐户还是外部 FTP）。Adobe 工程技术服务提供了几乎可通过任何方式发送的自定义[!UICONTROL 数据馈送]。

[!UICONTROL 数据馈送] FTP 帐户允许 2GB 或 63 个文件（默认情况下）。所有其他标准 FTP 帐户的默认限制为 50MB。在客户端将 FTP 帐户用于适当用途的情况下，某些高流量用户可快速填满这些帐户。当 FPT 帐户已填满时，不可再向其推送任何其他文件。因此，传送给该 FTP 帐户的任何文件（[!UICONTROL 数据馈送]、数据仓库请求等）都不会被传送。正因如此，通过删除已接收和下载的文件来管理 Adobe FTP 帐户才会如此重要。

当 FTP 帐户已填满时，您应当下载并删除当前的文件，并让 Adobe 知道空间已清理。Adobe 随后可以重新发送还未传送的文件。某些工具，如数据仓库，允许用户重新发送这些文件。重新发送可能不需要 Adobe 的介入。如果您的 FTP 帐户总是频繁被填满，请联系 Adobe 客户关怀，他们会建议您采用其他传送选项，以增加帐户上的 FTP 空间和文件数量配额。

有关 FTP 限制和数据保留的信息，请参阅[FTP 限制和数据保留](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E)。
