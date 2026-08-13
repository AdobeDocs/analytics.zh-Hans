---
description: 数据馈送是对 Adobe 收到的点击流数据的导出，其中提供标准和自定义数据馈送。
keywords: ftp;sftp
title: 数据馈送
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: 'https://experienceleague.adobe.com/JYiAXR-SbFNV3xQQ5Y1Qv10kVWpFJRWmuOvERcQ-zP4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 30%

---

# 数据馈送

>[!NOTE]
>
>以下信息与FTP和SFTP目标类型相关。 FTP 和 SFTP 都是旧版目标类型。 在配置数据馈送时，您应该使用云目标类型，这样更安全。 有关为数据馈送配置云目标类型的详细信息，请参阅[创建数据馈送](/help/export/analytics-data-feed/create-feed.md)。

数据馈送是对 Adobe 收到的点击流数据的导出，其中提供标准和自定义[数据馈送](/help/export/analytics-data-feed/data-feed-overview.md)。

如果您已购买 Adobe Data Warehouse、[!UICONTROL Standard Data Feeds]，则可以自行设置您自己的 Analytics 数据馈送。 它们可以发送到任何FTP帐户（由Adobe设置的帐户或外部FTP帐户）。 Adobe工程技术服务提供自定义[!UICONTROL 数据馈送]，几乎可以通过任何方式发送。

[!UICONTROL 数据馈送] FTP帐户允许10 GB（默认情况下）。 所有其他标准 FTP 帐户的默认限制为 50 MB。 如果客户端使用FTP帐户作为正常预期用途，则一些流量较大的用户可能会迅速填充这些帐户。 当FTP帐户已满时，无法向其推送其他文件。 因此，传送给该 FTP 帐户的任何文件（[!UICONTROL 数据馈送]、数据仓库请求等）都不会被传送。 这就是为什么必须通过删除已接收和下载的文件来管理Adobe FTP帐户的原因之一。

当FTP帐户已满时，您应该下载并删除当前文件，并告知Adobe空间已被清除。 然后，Adobe可以重新发送尚未提供的文件。 某些工具（如Data Warehouse）允许用户重新发送这些文件。 重新发送可能无需Adobe的参与。 如果您的FTP帐户似乎经常被占满，请联系Adobe客户关怀团队，他们可以提出交付替代方案，包括增加帐户的FTP空间和文件数量配额。
