---
title: 分类集概述
description: 使用分类集管理分类数据。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 84%

---

# 分类集概述

分类集提供单一界面来管理分类和规则。此工作流将在报表包设置中创建分类的概念，与分类导入程序的概念相结合，提供更直观的界面以供创建和管理分类数据。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]**

您必须是产品管理员或属于包含权限项[!UICONTROL 报表包工具] > [!UICONTROL 分类]的产品配置文件才能查看此菜单项。 请注意，尽管以前的分类管理界面位于[!UICONTROL 管理员]菜单下，但分类集位于[!UICONTROL 组件]菜单下。

## 改进

与分类集一起发布的后端架构包含几项显著改进：

* 缩短处理时间（72 小时 → 24 小时）
* 重新设计的用于管理分类的UI
* 未来通过[适用于分类数据的 Adobe Analytics Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/classifications) 在 Adobe Experience Platform 中使用分类数据的选项

与分类集一起发布的后端架构还包含几项显著更改：

* 使用浏览器或自动导入时，始终启用[!UICONTROL 冲突时覆盖]。
* 使用浏览器或自动导入时，不再支持导入后立即导出的选项。“导出”必须单独启动。
* Analytics 2.0 API `GetDimensions`端点现在返回用于分类的字符串标识符，而不是数字标识符。仍然可以使用数字标识符，但 Adobe 建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。

>[!IMPORTANT]
>
>分类集的性能主要取决于包含数据的唯一键值的数量。Adobe 建议谨慎处理包含大量唯一值的变量。将多个报表包和维度中的变量合并到单个分类集中时，尤其要注意这一点。

分类集包括三个主要方面：

* [**[!UICONTROL 分类集管理器]**](manage/set-manager.md)：创建、编辑和删除分类集。
* [**[!UICONTROL 分类集作业管理器]**](job-manager.md)：查看分类集作业的状态并下载导出文件。
* [**[!UICONTROL 分类集合并]**](consolidations/manage.md)：将多个分类集合并为一个统一的分类集。
