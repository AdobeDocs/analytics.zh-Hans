---
title: 创建分类集
description: 创建分类集时可用的字段和描述。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# 创建分类集

可以使用分类集管理器创建分类集。

>[!NOTE]
>
>此功能当前正在进行小范围发布。 如果您想访问此功能，请联系 Adobe 客户关怀部门或您的客户经理，他们可以将您的请求转发给分类团队进行配置。

**[!UICONTROL “组件”]**>**[!UICONTROL “分类集”]**>**[!UICONTROL “集”]**>**[!UICONTROL “添加”]**

创建分类集时，以下字段可用。

* **[!UICONTROL 名称]**：用于标识分类集的文本字段。 创建时无法编辑此字段，但可以稍后重命名。
* **[!UICONTROL 列名称]**：要创建的分类维度的名称。 此字段是分析工作区中使用的维度名称，以及导出分类数据时的列名。
* **[!UICONTROL 类型]**：显示分类类型的单选按钮。 通常使用初级分类；查找分类表示[子分类](../c-sub-classifications.md)。
* **[!UICONTROL 订阅]**：此分类集适用的报告包和维度。 计划支持多个报告包。

![创建分类集](../assets/classification-set-create.png)

如果给定报表套件+变量存在分类集，则将该分类添加到架构中。
