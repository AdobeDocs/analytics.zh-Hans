---
description: 管理员负责监控数据字典的运行状况。 这包括组件是否正在收集数据、是否获得批准、是否包含描述以及是否不存在重复项。
title: 监视数据字典运行状况
feature: Components
role: Admin
hide: true
hidefromtoc: true
source-git-commit: b0a3ee6785bdc2f3e9a55e42591b4846984934b6
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# 监视数据字典运行状况

{{release-limited-testing}}

Analytics管理员负责维护正常的数据字典。

## 健康数据字典的特点

健康的数据字典是所有组件之一：

* 正在使用并正在收集数据

* 包含有用的描述，以便用户了解如何最好地使用它们

* 没有不必要的重复项

* 经管理员批准

## 检查数据字典的运行状况

要在数据字典中确定运行状况问题，请执行以下操作：

1. 打开Analysis Workspace项目。

1. 选择Analysis Workspace左侧的“数据字典”图标。 (访问数据字典的替代方法在 [数据字典概述](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   此时将显示“数据字典”窗口。

   ![数据字典管理视图](assets/data-dictionary-admin.png)

1. 确保在下拉菜单中选择了正确的报表包。

1. 在 [!UICONTROL **字典健康**] 选项卡，选择 [!UICONTROL **查看**] 下列任意选项旁边的任意位置：

   * [!UICONTROL **组件缺少说明**]

   * [!UICONTROL **组件具有重复项**]

   * [!UICONTROL **组件没有连接数据**]

   根据您选择的内容，相应的过滤器会应用于数据字典，并且只显示相关的组件。

1. 编辑任何组件，以改善数据字典的运行状况。 有关如何在数据字典中编辑组件的信息，请参阅 [编辑数据字典中的组件条目](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).