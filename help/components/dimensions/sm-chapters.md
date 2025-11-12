---
title: 流媒体章节维度
description: 为报表包启用[!UICONTROL 媒体章节]时可用的维度。
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# 流媒体服务章节维度

*本页介绍了为报表包启用[!UICONTROL 媒体章节]时可用的维度。 有关可用量度，请参阅[流媒体服务章节量度](../metrics/sm-chapters.md)。*

流媒体服务章节维度通过流媒体服务库为数据收集提供补充报表功能。 使用这些维度需要&#x200B;**[!UICONTROL 适用于流媒体的Adobe Analytics加载项]**。 有关详细信息，请联系您的Adobe客户团队。

当您在&#x200B;**[!UICONTROL 媒体报告]**&#x200B;下启用[媒体章节](/help/admin/tools/manage-rs/edit-settings/media-management.md)时，以下维度可用：

| 维度名称 | 描述 | 发送条件 | 上下文数据变量 | XDM字段 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 章节]** | 自动生成的章节ID。 | 章节关闭 | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

除了上述维度之外，Adobe还会自动创建以下分类维度。 您必须上传分类数据，以查看使用这些维度的报表。

| 分类名称 | 父维度 | 描述 |
| --- | --- | --- |
| **[!UICONTROL 发起人]** | [[!UICONTROL 内容]](sm-core.md) | 内容的创作者。 |
| **[!UICONTROL 章节长度]** | [!UICONTROL 章节] | 章节的长度，以秒为单位。 |
| **[!UICONTROL 章节名称]** | [!UICONTROL 章节] | 章节的友好名称。 |
| **[!UICONTROL 章节偏移]** | [!UICONTROL 章节] | 内容中章节从开始到现在的偏移，以秒为单位。 |
| **[!UICONTROL 章节位置]** | [!UICONTROL 章节] | 内容中章节的索引位置。 |
