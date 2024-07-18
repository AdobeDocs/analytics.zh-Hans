---
description: 数据馈送是对 Adobe 收到的点击流数据的导出，其中提供标准和自定义数据馈送。
keywords: ftp;sftp
title: 数据馈送
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 05b4dc07de567b25e71b47fd92743bee0b5621f8
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 82%

---

# 数据馈送

>[!NOTE]
>
>以下信息与FTP和SFTP目标类型相关。 FTP和SFTP是旧版目标类型。 在配置数据馈送时，您应该使用云目标类型，这样更安全。 有关为数据馈送配置云目标类型的详细信息，请参阅[创建数据馈送](/help/export/analytics-data-feed/create-feed.md)。

数据馈送是对 Adobe 收到的点击流数据的导出，其中提供标准和自定义[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已购买 Adobe Data Warehouse、[!UICONTROL Standard Data Feeds]，则可以自行设置您自己的 Analytics 数据馈送。可将它们发送到任何 FTP 帐户（无论是由 Adobe 设置的帐户还是外部 FTP）。Adobe 工程技术服务提供了几乎可通过任何方式发送的自定义[!UICONTROL 数据馈送]。

[!UICONTROL 数据馈送] FTP帐户允许10 GB（默认情况下）。 所有其他标准 FTP 帐户的默认限制为 50 MB。在客户端将 FTP 帐户用于适当用途的情况下，某些高流量用户可快速填满这些帐户。当 FPT 帐户已填满时，不可再向其推送任何其他文件。因此，传送给该 FTP 帐户的任何文件（[!UICONTROL 数据馈送]、数据仓库请求等）都不会被传送。正因如此，通过删除已接收和下载的文件来管理 Adobe FTP 帐户才会如此重要。

当 FTP 帐户已填满时，您应当下载并删除当前的文件，并让 Adobe 知道空间已清理。Adobe 随后可以重新发送还未传送的文件。某些工具，如数据仓库，允许用户重新发送这些文件。重新发送可能不需要 Adobe 的介入。如果您的 FTP 帐户总是频繁被填满，请联系 Adobe 客户关怀，他们会建议您采用其他传送选项，以增加帐户上的 FTP 空间和文件数量配额。
