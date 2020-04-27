---
description: 计划报表时，您可以选择要用于分发的发布列表。
title: 允许发布列表覆盖
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 允许发布列表覆盖

计划报表时，您可以选择要用于分发的发布列表。

发布列表在 Analytics 管理工具中进行设置。

请参阅 Analytics 参考资料中的[发布列表管理器](https://marketing.adobe.com/resources/help/zh_CN/reference/publishing_list.html)。

要启用此功能，请导航到该 [!UICONTROL Request Wizard: Step 1] 窗口。

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. 此外，如果工作簿包含多个报表包，则使用与发布列表相关联的报表包 ID。

对于从单元格中选择的报表包，该选项不可用。

>[!NOTE]如果将计划报表发送给多个发布列表，则报表针对每个列表运行一次。可变报表包由分配给发布列表的报表包替换。

