---
title: 分类集设置
description: 创建或编辑分类集。
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 分类集设置

配置分类集、上载数据或下载数据。

**[!UICONTROL 组件]** > **[!UICONTROL 分类集]** > **[!UICONTROL 集]** >单击所需的分类集名称

在编辑分类集时，有两个选项卡可用； **[!UICONTROL 架构]** 和 **[!UICONTROL 设置]**.

## 设置

在 [!UICONTROL 设置] 选项卡，并且可以编辑：

* **[!UICONTROL 名称]**:分类集名称。
* **[!UICONTROL 描述]**:分类集的描述。
* **[!UICONTROL 所有者名称]**:所有者名称。
* **[!UICONTROL 所有者电子邮件]**:所有者的电子邮件地址。
* **[!UICONTROL 通知问题]**:此分类集中出现问题的通知的电子邮件地址列表（以逗号分隔）。
* **[!UICONTROL 标记]**:向选定的分类集添加一个或多个标记，以便您组织或分组分类集，以便将来更便于查找。

其他字段可供参考，且无法编辑：

* **[!UICONTROL 类型]**:之间的分类类型 [!UICONTROL 主要] 和 [!UICONTROL 查找]. 通常使用主要分类。
* **[!UICONTROL 订阅]**:分类集所应用的报表包和变量。 给定分类集当前仅支持一个报表包；计划会支持多个报表包。

## 架构

查看当前为此订阅配置的分类维度。 可以使用以下按钮：

* **[!UICONTROL 上传]**:手动上载一个或多个分类维度的分类数据。 支持JSON、CSV、TSV和TAB文件。 上传有效文件会显示要分类的数据的表预览。
   * **[!UICONTROL 文件编码]**:使用此下拉菜单选择正确的文件编码。 有效选项包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1].
   * **[!UICONTROL 列表分隔符]**:选择正确的列表分隔符。 如果使用下载的文件或模板文件，请确保 [!UICONTROL 列表分隔符] 此处匹配 [!UICONTROL 列表分隔符] 文件下载时。
   * **[!UICONTROL 应用]**:将上载的分类数据保存到分类集。
