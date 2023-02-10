---
title: 分类集概述
description: 使用分类集管理分类数据。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 2ba6ffc7f632975ca16fa02ee79d467d4d53f076
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 45%

---

# 分类集概述

分类集提供单一界面来管理分类和规则。 此工作流将在报告包设置中创建分类的概念，与分类导入器的概念相结合，提供更直观的界面以供创建和管理分类数据。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]**

>[!NOTE]
>
>所有将其报表包迁移到新分类架构的客户都可以使用分类集。请联系 Adobe 客户关怀部门或您的客户经理以获取更多信息。

随分类集一起发布的后端架构包含一些显着改进：

* 显着缩短了处理时间(72小时→24小时)
* 使用分类集UI的功能
* 将来可通过使用 [Adobe Analytics源连接器用于分类数据](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

随分类集一起发布的后端架构还包含若干显着更改：

* 使用浏览器或FTP导入时，&#39;[!UICONTROL 冲突时覆盖]始终启用“ ”。
* 使用浏览器或FTP导入时，不再支持导入后立即导出的选项。 必须单独启动导出。
* Analytics 2.0 API `GetDimensions` 端点现在会返回分类的字符串标识符，而不是数字标识符。 数字标识符仍可以使用，但Adobe建议尽可能使用新的字符串标识符。 数字标识符可使用 `?expansion=hidden` 查询字符串参数。


分类集包括两个主要方面：

* [**[!UICONTROL 分类集管理器]**](set-manager.md)：创建、编辑和删除分类集。
* [**[!UICONTROL 分类集作业管理器]**](job-manager.md)：查看分类集作业的状态并下载导出文件。
