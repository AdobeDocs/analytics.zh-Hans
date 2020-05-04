---
description: Quick Insights Builder是面向新Workspace用户的工具，可指导他们构建数据表和可视化
title: 快速洞察构建器
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# 快速洞察构建器

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** 目前处于有限测试状态，并非所有Adobe Analytics客户都能使用。

[!UICONTROL Quick Insights] 为非分析师和新用户提供指导， [!UICONTROL Analysis Workspace] 了解如何快速轻松地回答业务问题。 对于希望快速回答简单问题的高级用户来说，它也是一个不错的工具，无需自己构建表。

首次使用此开始 [!UICONTROL Analysis Workspace]时，您可能会想知道哪些可视化功能最有用，哪些维度和指标可以促进洞察、在何处拖放项目、在何处创建区段等。

为此，并根据公司在中对数据组件的使用情况 [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] 利用一种算法，它将为您提供公司使用的最流行的维度、指标、细分和日期范围。

[!UICONTROL Quick Insights] 帮助您

* 请在中正确构建数据表和随附的可视化 [!UICONTROL Analysis Workspace]。
* 了解基本组件和部分的术语和词汇 [!UICONTROL Analysis Workspace]。
* 对维度进行简单细分、添加多个指标或在其中轻松比较区段 [!UICONTROL Freeform table]。
* 更改或尝试各种可视化类型，快速、直观地找到适合您的分析的查找工具。

## 基本关键术语

以下是您需要熟悉的一些基本术语。 每个数据表都包含2个或多个用于讲述数据故事的构件块（组件）。

| 构建块（组件） | 定义 |
|---|---|
| [!UICONTROL Dimension] | 维是度量数据的描述或特性，可在项目中查看、细分和比较。 它们是非数字值和日期，可划分为维项目。 例如，“browser”或“page”是维。 |
| [!UICONTROL Dimension item] | 维项是维的单个值。 例如，浏览器维度的维度项应为“Chrome”、“Firefox”、“Edge”等。 |
| [!UICONTROL Metric] | 量度是有关访客活动的量化信息，包括查看次数、点进次数、重新加载次数、平均逗留时间、件数、订购、收入等。 |
| [!UICONTROL Visualization] | 工作区 [优惠多种可视化](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ，以构建数据的可视化表示形式，如条形图、圆环图、直方图、直线图、地图、散点图等。 |
| [!UICONTROL Breakdown] | 细分是一种按其他维度来划分维度的方法。 在我们的示例中，您可以按移动设备划分美国州，以获取每个州的移动设备访问次数，或按移动设备类型、地区、内部活动等划分移动设备。 |
| [!UICONTROL Segment] | 细分允许您根据特征或网站交互确定访客子集。 例如，您可以根据属 [!UICONTROL Visitor] 性构建区段： 浏览器类型、设备、访问次数、国家／地区、性别或基于交互： 活动、关键字搜索、搜索引擎或基于退出和条目： 来自Facebook、已定义登陆页、引用域或基于自定义变量的访客: 表单字段、定义的类别、客户ID。 |

## 快速洞察入门

1. 使用您提供的凭据登录到Adobe Analytics。
1. 转到并 [!UICONTROL Workspace] 单击， **[!UICONTROL Create New Project]** 然后单击 **[!UICONTROL Quick Insights]**。

   ![](assets/qibuilder.png)

1. 当您第一次开始时，请阅读简短的教程，它教您一些基础 [!UICONTROL Quick Insights panel] 知识。 或者，单击 **[!UICONTROL Skip Tutorial]**。
1. 选择构件块（也称为组件）: 维（橙色）、度量（绿色）、段（蓝色）或日期范围（紫色）您必须为要自动构建的表至少选择一个维度和一个度量。

   ![](assets/qibuilder2.png)

   您有三种选择构造块的方法：
   * 从左边栏拖放它们。
   * 如果您知道要查找的内容： 开始键 [!UICONTROL Quick Insights] 入并将填入空白。
   * 单击下拉框并搜索列表。

1. 添加至少一个维和一个度量后，将为您创建以下内容：

   * 一个自由形式表，其顶部为垂直尺寸（此处为美国州）和水平度量（此处为访问量）。 请查看此表：
   ![](assets/qibuilder3.png)

   * 随附的可视化，本例为条 [形图](/help/analyze/analysis-workspace/visualizations/bar.md)。 生成的可视化基于您添加到表中的数据类型。 您可以通过单击旁边的下拉箭头来更改可视化类型 **[!UICONTROL Bar]**。


1. （可选）通过单击维旁的>向右箭头，向下展开维并查看维项。

1. 尝试添加一些更多的细化，如“其他有用选项”下所述。

## 其他有用选项

其他有用的提示将弹出到 [!UICONTROL Quick Insights Builder]中，其中一些提示取决于您的上一个操作。

* 首先，完成教 **[!UICONTROL More tips]** 程： 通过帮助(?)访问它 图标。 [!UICONTROL Quick Insights Panel]

   ![](assets/qibuilder4.png)

* **细分依据**: 您最多可以对维度使用3个级别的细分，以细化您真正需要的数据。

   ![](assets/qibuilder5.png)

* **添加更多指标**: 使用AND运算符将多达2个指标添加到表中。

   ![](assets/qibuilder6.png)

* **添加更多区段**: 使用AND或OR运算符将多达2个区段添加到表中。 查看添加移动用户或忠诚访客时表格会发生什么情况。 它们彼此相邻，高于指标。 如果您添加了“移动用户”和“忠诚访客”，您将看到这两个细分的结果，并且它们会放在表中彼此之上。

   ![](assets/qibuilder7.png)

## 已知限制

如果尝试直接在表中进行编辑， [!UICONTROL Quick Insights] 将导致面板（填空工具）不同步。 单击面板右上 [!UICONTROL Quick Insights] 方，可将 **[!UICONTROL Resync Builder]** 其恢复为之前的设置。

![](assets/qibuilder9.png)

在将任何内容直接添加到表之前，您会收到警告：

![](assets/qibuilder8.png)

否则，直接构建将导致表现为传统的自由形式表，而新用户没有有用的功能。

