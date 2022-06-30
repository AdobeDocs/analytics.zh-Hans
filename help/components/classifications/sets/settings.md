---
title: 分类集设置
description: 创建或编辑分类集。
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 100%

---

# 分类集设置

配置分类集、上载数据或下载数据。

>[!NOTE]
>
>此功能当前正在进行小范围发布。 如果您想访问此功能，请联系 Adobe 客户关怀部门或您的客户经理，他们可以将您的请求转发给分类团队进行配置。

**[!UICONTROL “组件”]**>**[!UICONTROL “分类集”]**>**[!UICONTROL “集”]**>“单击所需的分类集名称”

编辑分类集时，有两个选项卡可用，即&#x200B;**[!UICONTROL 架构]**&#x200B;和&#x200B;**[!UICONTROL 设置]**。

## 设置

以下字段在[!UICONTROL 设置]选项卡中可用，可以编辑：

* **[!UICONTROL 名称]**：分类集名称。
* **[!UICONTROL 描述]**：分类集描述。
* **[!UICONTROL 所有者名称]**：所有者名称。
* **[!UICONTROL 所有者电子邮件]**：所有者电子邮件地址。
* **[!UICONTROL 通知问题]**：通知此分类集问题的电子邮件地址的逗号分隔列表。
* **[!UICONTROL 标记]**：将一个或多个标记添加到选定的分类集，使您能够梳理或分组分类集，以便将来更容易查找。

其他字段可用于提供信息，无法编辑：

* **[!UICONTROL 类型]**：[!UICONTROL “主要查找”] 与[!UICONTROL “查找”]之间的分类类型。 通常使用初级分类。
* **[!UICONTROL 订阅]**：分类集应用的报告包和变量。 此时，给定分类集仅支持一个报告包；计划支持多个报告包。

## 架构

查看此订阅当前配置的分类维度。 以下按钮可供使用：

* **[!UICONTROL 上载]**：手动上载一个或多个分类维度的分类数据。 支持 JSON、CSV、TSV 和 TAB 文件。 上载有效文件会显示要分类的数据的表预览。
   * **[!UICONTROL 文件编码]**：使用此下拉列表选择正确的文件编码。 有效选项包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。
   * **[!UICONTROL 列表分隔符]**：选择正确的列表分隔符。如果使用下载的文件或模板文件，请确保此处的[!UICONTROL 列表分隔符]与下载文件时的[!UICONTROL 列表分隔符]匹配。
   * **[!UICONTROL 应用]**：将上载的分类数据保存到分类集。

   ![分类集上载](../assets/classification-set-upload.png)

* **[!UICONTROL 下载]**：下载键值及其分类列。
   * **[!UICONTROL 行]**：下载文件中包含的最大行数。
   * **[!UICONTROL 下载在报告中出现的键值之间接收的行]**：日历日期选择器，允许您按键值出现的时间筛选键值。如果未在此日期范围内收集键值，则该键值不会显示在下载的文件中。
   * **[!UICONTROL 返回的数据]**：一个下拉列表，允许您根据相关分类数据筛选下载文件中包含的键值。
      * **[!UICONTROL 所有已分类的值]**：包括分类数据至少包含在一列中的行。
      * **[!UICONTROL 所有未分类的值]**：包括至少一列中缺少分类数据的行。
   *  **[!UICONTROL 文件格式]**：确定下载文件的文件格式的下拉列表。选项包括 [!UICONTROL JSON]、[!UICONTROL 逗号分隔的值]和 [!UICONTROL Excel 选项卡分隔的数值]。
   * **[!UICONTROL 文件编码]**：确定文件编码的下拉列表。 选项包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。 建议使用 UTF-8。
   * **[!UICONTROL 列表分隔符]**：确定分隔每行分类列的列表分隔符的下拉列表。

   ![分类集下载](../assets/classification-set-download.png)

* **[!UICONTROL 模板]**：下载模板文件。 此文件类似于[!UICONTROL “下载”]按钮，只是它不包含任何分类数据或键值。
   *  **[!UICONTROL 文件格式]**：确定模板文件所在文件格式的下拉列表。选项包括[!UICONTROL 逗号分隔的值]和 [!UICONTROL Excel 选项卡分隔的数值]。
   * **[!UICONTROL 文件编码]**：确定文件编码的下拉列表。 选项包括 [!UICONTROL UTF-8] 和 [!UICONTROL Latin1]。 建议使用 UTF-8。
   * **[!UICONTROL 列表分隔符]**：确定分隔每行分类列的列表分隔符的下拉列表。
* **[!UICONTROL 作业历史记录]**：一个快捷链接，将您带到[作业管理器](job-manager.md)，仅显示此分类集的作业。

   ![分类集模板](../assets/classification-set-template.png)
