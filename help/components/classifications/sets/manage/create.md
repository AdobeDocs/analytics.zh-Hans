---
title: 创建分类集
description: 创建分类集时可用的字段和描述。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 22%

---

# 创建分类集

您可以使用分类集管理器创建分类集。

**[!UICONTROL “组件”]**>**[!UICONTROL “分类集”]**>**[!UICONTROL “集”]**>**[!UICONTROL “添加”]**

创建分类集时，以下字段可用。

* **[!UICONTROL 名称]**：用于标识分类集的文本字段。 创建时无法编辑此字段，但可以稍后重命名。
* **[!UICONTROL 列名称]**：要创建的第一个分类维度的名称。 此字段是Analysis Workspace中使用的维度名称，以及导出分类数据时的列名称。 创建分类集后，您可以添加更多列名称。
* **[!UICONTROL 类型]**：显示分类类型的单选按钮。 通常使用初级分类；查找分类表示[子分类](../../c-sub-classifications.md)。
* **[!UICONTROL 订阅]**&#x200B;此分类集适用的报表包和维度。 您可以将多个报表包和维度组合添加到分类集。

![创建分类集](../../assets/classification-set-create.png)

如果给定报表包+变量存在分类集，则将该分类添加到架构中。 给定的报表包+变量组合不能属于多个分类集。
