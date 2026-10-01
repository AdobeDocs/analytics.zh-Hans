---
description: 了解计算量度构建器，它提供了一个画布，您可以通过拖放维度、量度、区段和函数，基于容器层级逻辑、规则和运算符创建自定义量度。
title: 生成度量
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
TQID: https://experienceleague.adobe.com/ds8aD51DynOEJ7uYZ5Id-kTng2JPN4nZYuMTaKj-ZvE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
    internal-label: Workspace projects
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 8badbfc74bdc95a8ab673d4f00fe13e0829e64bb
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 99%
---
# 生成计算量度 {#build-metrics}

Adobe Analytics 提供了一个画布，用于拖放维度、量度、区段和函数，以基于容器层级逻辑、规则和运算符创建自定义量度。 通过这种集成式开发工具，您可以生成并保存简单或复杂的计算量度。

您可以使用计算量度生成器来创建或编辑计算量度。 以这种方式创建时，计算量度可在组件列表中使用，然后可在整个组织的项目中使用。 或者，您可以快速创建仅适用于创建它的项目的计算量度，如[量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)中[为单个项目创建计算量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)所述。

[创建计算量度](../cm-workflow.md)介绍了用于创建新计算量度的各类可用选项。

## 计算量度构建器的区域

**[!UICONTROL 计算量度生成器]**&#x200B;对话框用于创建新的或编辑现有的计算量度。 对于您在[[!UICONTROL 计算量度]管理器](../cm-manager.md)中创建或管理的量度，该对话框的标题为&#x200B;**[!UICONTROL 新建计算量度]**&#x200B;或&#x200B;**[!UICONTROL 编辑计算量度]**。

>[!BEGINTABS]

>[!TAB 计算量度生成器]

![计算量度详情窗口，其中显示下一节所述的字段和选项。](assets/calculated-metric-builder.png)

>[!TAB 创建或编辑计算量度]

![计算量度详情窗口，其中显示下一节所述的字段和选项。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 指定以下详细信息（![Required](/help/assets/icons/Required.svg)为必要项）：

   | 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 报告包]** | 您可以为计算量度选择报告包。  您定义的计算量度将在基于所选报告包的 Workspace 项目中可用。 |
   | **[!UICONTROL 仅限于项目的量度]** | 当您编辑为单个项目创建的计算量度时，此对话框顶部会出现一个信息框，如[为单个项目创建计算量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)中所述。 <p>如果您希望将此计算量度用于所有项目，请选择以下选项：**[!UICONTROL 将此量度提供给所有项目并将其添加到组件列表中]**。</p> |
   | **[!UICONTROL 标题]**![必填](/help/assets/icons/Required.svg) | 为计算量度命名，例如，`Conversion Rate`。 |
   | **[!UICONTROL 描述]** | 提供对区段的描述，例如：`Calculated metric to define the conversion rate.` 无需描述计算量度的公式，因为[!UICONTROL 摘要]中已自动提供该公式。 |
   | **[!UICONTROL 格式]** | 选择计算量度的格式：您可以选择&#x200B;**[!UICONTROL 小数]**、**[!UICONTROL 时间]**、**[!UICONTROL 百分比]**&#x200B;和&#x200B;**[!UICONTROL 货币]**。 |
   | **[!UICONTROL 小数位]** | 指定所选格式的小数位数。 仅当选择的格式为十进制、货币和百分比时启用。 |
   | **[!UICONTROL 将上升趋势显示为]** | 指定计算量度的上升趋势是否显示为 ▲ **[!UICONTROL 良好（绿色）]**&#x200B;或 ▼ **[!UICONTROL 不良（红色）]**。 |
   | **[!UICONTROL 货币]** | 指定计算量度的货币。 仅当选择的格式为货币时才启用。 |
   | **[!UICONTROL 标记]** | 通过创建或应用一个或多个标记来组织计算量度。 开始键入，以查找您可以选择的现有标记。 或者按&#x200B;**[!UICONTROL 输入]**&#x200B;键添加新的标记。 选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以移除标记。 |
   | **[!UICONTROL 预览]** | 预览涵盖过去 90 天的情况，并且可以衡量您是否正确定义了量度。 |
   | **[!UICONTROL 摘要]** | 显示计算量度定义的摘要。 <br/>例如：![事件](/help/assets/icons/Event.svg) **[!UICONTROL 总订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话]**。 |
   | **[!UICONTROL 定义]**![必填](/help/assets/icons/Required.svg) | 使用[定义生成器](#definition-builder)来定义区段。 |

1. 要验证您的计算量度定义是否正确，请使用不断更新的计算量度结果&#x200B;**[!UICONTROL 预览]**。 **[!UICONTROL 预览]**&#x200B;涵盖过去 90 天，并会持续评估计算量度的定义。

   **[!UICONTROL 产品兼容性]**&#x200B;表示该计算量度与 Adobe Analytics 各项功能的兼容情况。 请参阅[量度兼容性](/help/components/calculated-metrics/cm-compatibility.md)，以了解更多信息。

1. 选择:
   * **[!UICONTROL 保存]**&#x200B;以保存计算量度。
   * **[!UICONTROL 另存为]**&#x200B;以保存计算量度的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消您对计算量度所做的任何更改，或者取消创建新的计算量度。


## 定义生成器

您可以使用定义生成器来拖放维度、量度、区段和函数，以根据容器层级结构逻辑、规则和运算符来创建自定义量度。 在该构造中，您可以使用标准度量、Adobe 定义的度量、计算度量、区段、维度和函数。 所有这些组件都可以从计算量度生成器中的组件面板中获得。 此外，您还可以在定义中使用运算符和容器。

![创建计算量度](assets/create-calculated-metric.gif)

在&#x200B;**[!UICONTROL 定义]**&#x200B;区域中，仅会将量度定义为单一组件。 所有其他组件都定义为容器，用于包装量度或其他容器。 有关更多信息，请参阅[容器](#containers)。

### 量度

要添加量度：

* 将![事件](/help/assets/icons/Event.svg)**[!UICONTROL 量度]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。

当您使用计算量度作为定义的一部分时，计算量度将会展开。

要修改量度：

1. 在![定义](/help/assets/icons/Setting.svg)区域中的量度组件中选择&#x200B;**[!UICONTROL 设置]**。
1. 在弹出对话框中，您可以定义量度的类型和归因模型。 请参阅[量度类型和归因](m-metric-type-alloc.md)。

要删除量度：

* 在量度中选择![关闭](/help/assets/icons/Close.svg)。

### 运算符

运算符允许您指定组件或容器之间的运算符。 运算符自动出现在

* 容器中的两个或多个量度，
* 容器中的两个或多个容器，
* 容器中的一个或多个量度以及一个或多个容器。

您可以选择︰

| 符号 | 运算符 |
|:---:|---|
| ![除](/help/assets/icons/Divide.svg) | 除（默认） |
| ![关闭](/help/assets/icons/Close.svg) | 乘 |
| ![删除](/help/assets/icons/Remove.svg) | 减 |
| ![加](/help/assets/icons/Add.svg) | 加 |

### 静态数字

您可以向计算量度定义中添加一个静态数字。 要添加一个静态数字：

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**。
* 选择&#x200B;**[!UICONTROL 静态数字]**。 出现静态数字容器。
* 选择&#x200B;[!UICONTROL *单击以添加值*]&#x200B;并输入一个值。


### 容器

您可以将维度、区段和函数作为容器添加到计算量度定义中。 您还可以添加通用容器。 容器的作用类似于数学表达式，它们决定着运算的顺序。 容器内的任何内容都会在下一个组件或容器之前得到处理。


#### 区段容器

您可以使用区段容器的概念来创建[分段量度](metrics-with-segments.md)。 您可以使用区段或者使用从某个维度创建的区段来构建区段容器。

* 要从某个维度添加区段容器：

  1. 将![维度](/help/assets/icons/Dimensions.svg) **[!UICONTROL 维度]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。
  1. 在&#x200B;**[!UICONTROL 从维度创建区段]**&#x200B;弹出窗口中，定义该区段的条件。 从运算符列表中选择，并选择一个值或输入一个值。 例如，**[!UICONTROL 月份]**&#x200B;**[!UICONTROL 等于]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`。
  1. 选择&#x200B;**[!UICONTROL 完成]**。 现在，**[!UICONTROL 定义]**&#x200B;中添加了一个区段容器。


* 要从某个区段添加区段容器，您可以使用：

  * 将![分段](/help/assets/icons/Segmentation.svg)**[!UICONTROL 区段]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定区段。
    使用区段的名称，区段容器被自动添加到&#x200B;**[!UICONTROL 定义]**&#x200B;中。

  * 将![分段](/help/assets/icons/Segmentation.svg)**[!UICONTROL 区段]**&#x200B;组件从组件面板拖放到通用容器上。 该容器变成了一个区段容器。

  * 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**：

    1. 选择&#x200B;**[!UICONTROL 区段]**。 现在，**[!UICONTROL 定义]**&#x200B;中添加了一个区段容器。
    1. 在这个新的区段容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个区段。

  >[!TIP]
  >
  >您可以在一个容器中添加多个区段。

  容器中的区段以区段组件命名。 例如，![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web 会话]**。 选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 可显示一个包含区段详细信息的弹出窗口。 在这个弹出窗口中，选择![编辑](/help/assets/icons/Edit.svg)可编辑区段定义。

要从容器中移除某个区段：

* 选择区段名称旁边的![关闭](/help/assets/icons/Close.svg)。

有关更多详细信息和示例，请参阅[区段化量度](metrics-with-segments.md)。

#### 函数容器

要添加函数容器，您可以使用：

* 拖放：

  1. 将 ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL 函数]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定函数。
  1. 使用函数的名称自动将函数容器添加到&#x200B;**[!UICONTROL 定义]**。

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**：

  1. 选择&#x200B;**[!UICONTROL 函数]**。
  1. 在容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个函数。

函数容器以函数组件命名。 例如，![函数](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度）]**。 选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 来显示一个带有函数详细信息的弹出窗口。 选择&#x200B;**[!UICONTROL 了解更多]**，以了解有关该函数的更多信息。

请参阅[使用函数](cm-using-functions.md)，了解有关如何使用函数以及可以使用哪些函数来创建计算量度的详细信息。


#### 通用容器

要添加通用容器：

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**
* 选择&#x200B;**[!UICONTROL 容器]**。 **[!UICONTROL 定义]**&#x200B;中添加了一个新的空容器。 您可以使用通用容器在计算量度的定义中嵌套或创建层级结构。


#### 删除容器

要删除容器，请在容器级别选择![关闭](/help/assets/icons/Close.svg)。

>[!MORELIKETHIS]
>
>[使用函数](cm-using-functions.md)
>[区段](/help/components/segmentation/seg-overview.md)
>
