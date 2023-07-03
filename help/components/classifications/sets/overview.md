---
title: 分类集概述
description: 使用分类集管理分类数据。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# 分类集概述

分类集提供单个界面来管理分类和规则。 此工作流将在报表包设置中创建分类的概念与分类导入器的概念相结合，以提供更直观的界面来创建和管理分类数据。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]**

与分类集一起发布的后端架构包含几项显着改进：

* 缩短处理时间(72小时→24小时)
* 能够使用分类集UI
* 未来通过[适用于分类数据的 Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html) 在 Adobe Experience Platform 中使用分类数据的选项

随分类集一起发布的后端架构还包含几项显着更改：

* 使用浏览器或自动导入时， &#39;[!UICONTROL 发生冲突时覆盖]”始终处于启用状态。
* 使用浏览器或自动导入时，不再支持导入后立即导出的选项。 “导出”必须单独启动。
* Analytics 2.0 API `GetDimensions`端点现在返回用于分类的字符串标识符，而不是数字标识符。仍然可以使用数字标识符，但 Adobe 建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。

>[!IMPORTANT]
>
>分类集的性能主要取决于包含数据的唯一键值的数量。 Adobe建议在处理包含大量唯一值的变量时务必谨慎。 将多个报告包和维度的变量组合到一个分类集中时，此警告尤其适用。

分类集包括三个主要领域：

* [**[!UICONTROL 分类集管理器]**](manage/set-manager.md)：创建、编辑和删除分类集。
* [**[!UICONTROL 分类集作业管理器]**](job-manager.md)：查看分类集作业的状态并下载导出文件。
* [**[!UICONTROL 分类集合并]**](consolidations/manage.md)：将多个分类集合并到一个分类集中。
