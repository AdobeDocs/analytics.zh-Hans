---
title: 创建注释
description: 如何在工作区中创建注释。
role: User, Admin
source-git-commit: f8a928782b4c4916f5ff2042cb72941d76f57d7d
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---


# 创建注释

>[!NOTE]
>
>此功能当前处于有限测试阶段。

1. 要创建注释，您有4种入门方法：

   * 转到 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 注释]. 此时将打开“注释管理器”页面。 单击 [!UICONTROL 创建新注释] 和注释生成器打开，或

   * 右键单击表或折线图上的点。 将打开注释生成器，或

   * 在工作区中，转到 [!UICONTROL 组件] > [!UICONTROL 创建注释].

   * 使用此热键打开注释生成器：
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. 填写生成器元素。

   ![](assets/ann-builder.png)

   | 元素 | 描述 |
   | --- | --- |
   | [!UICONTROL 标题] | 命名注释，例如“纪念日” |
   | [!UICONTROL 描述] | （可选）提供注释的描述，例如“美国观看公共假日”。 |
   | [!UICONTROL 标记] | （可选）通过创建或应用标记来组织批注。 |
   | [!UICONTROL 应用的日期] | 选择注释需要存在的日期或日期范围才可见。 |
   | [!UICONTROL 颜色] | 将颜色应用于注释。 注释以所选颜色显示在项目中。 可以使用颜色对批注进行分类，例如公共假日、外部事件、跟踪问题等。 |
   | [!UICONTROL 范围] | （可选）拖放触发注释的量度。 然后，拖放任何充当过滤器的维度或区段（即，批注将随之显示）。 如果未指定范围，则注释将应用于所有数据。<ul><li>**[!UICONTROL 以下任何量度都存在]**:拖放最多10个将触发要显示注释的量度。</li><li>**[!UICONTROL 使用所有这些过滤器]**:拖放最多10个维度或区段，以在注释显示时进行过滤。</li></ul><p>用例：eVar已停止收集特定日期范围的数据。 将eVar拖入 **[!UICONTROL 以下任何量度都存在]** 对话框。 或 [!UICONTROL 访问次数] 量度未报告任何数据 — 请遵循相同的流程。 |
   | [!UICONTROL 应用于所有报告包] | 默认情况下，注释适用于原始报表包。 勾选此框后，您可以将注释应用于公司中的所有报表包。 |
   | [!UICONTROL 应用于所有项目] | 默认情况下，注释应用于当前项目。 勾选此框后，注释可应用于您拥有的所有项目。 |

1. 单击[!UICONTROL 保存]。