---
description: 在 Workspace 项目中使用流可视化。
title: 配置流量可视化图表
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: a90e754e50c0e7325d20a0a9436dab751d1a5f09
workflow-type: tm+mt
source-wordcount: '1415'
ht-degree: 43%

---

# 配置流量可视化图表

流量可视化图表可帮助您了解源于或导致网站或应用程序上特定转化事件的历程。它通过维度（和维度项）或量度跟踪路径。

流量可视化图表可让您配置感兴趣的路径的起点或终点，或分析流经某个维度或维度项的所有路径。

![新的流量 UI](assets/new-flow.png)

## 使用

1. 添加![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 使用以下选项之一锚定流量可视化图表：

   * 以（量度、维度或项目）[!UICONTROL **开头**]，或
   * [!UICONTROL **包含**]（维度或项目），或
   * 以（量度、维度或项目）[!UICONTROL **结束**]

   这些类别均在屏幕上显示为&#x200B;*放置区域*。 可以通过3种方式填充放置区域：

   * 使用下拉菜单选择量度或维度。
   * 从左侧面板拖动维度或量度。
   * 开始键入维度或量度的名称，然后在它出现在下拉列表中时将其选中。

   >[!IMPORTANT]
   >
   >计算量度不能在&#x200B;**[!UICONTROL Starts with]**&#x200B;或&#x200B;**[!UICONTROL Ends with]**&#x200B;字段中使用。

1. 如果您选择某个量度，则还需要提供一个&#x200B;[!UICONTROL **路径Dimension**]，用作通往或离开您选定组件的路径，如下所示。 默认的是 [!UICONTROL **页面**]。

   ![流配置](assets/flow-configure.png)

1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以配置以下任一选项：


   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 包装标签]** | 通常情况下，流量元素上的标签会被截断以节约屏幕资源，但您可以通过选中此框使整个标签可见。默认值 = 取消选中。 |
   | **[!UICONTROL 包括重复实例]** | 流量可视化内容基于某个维度的实例。此设置使您可以选择包含或排除重复的实例，例如，页面重新加载。 但是，不能从包含多值维度（例如 listVar、listProp、s.product、推销 eVar 等）的流量可视化图表中删除重复项。 <p>默认禁用此选项。</p> |
   | **[!UICONTROL 限制到第一次/最后一次发生次数]** | 将路径限制为以维度、项目或量度的第一次或最后一次发生次数开头或结尾的路径。 有关更详细的说明，请参阅[限制到第一次/最后一次发生次数](#example-scenario-for-limit-to-firstlast-occurrence)。 |
   | **[!UICONTROL 列数]** | 流量图中所需的列数。您最多可以指定 5 个列。 |
   | **[!UICONTROL 每列扩展的项]** | 每列中所需的项数。您最多可以指定每列扩展 10 个项。 |
   | **[!UICONTROL 流量容器]** | 您可以在&#x200B;**[!UICONTROL 会话]**&#x200B;和&#x200B;**[!UICONTROL 人员]**&#x200B;之间切换以分析路径。 这些设置可帮助您了解个人在人员级别（跨会话）的参与度，或将分析限制在单个会话。 |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 列数]**&#x200B;和&#x200B;**[!UICONTROL 每列扩展的项]**&#x200B;的组合确定创建流量可视化图表所需的基础请求数。该数量越多，渲染可视化图表所需的时间就越长。


1. 选择&#x200B;**[!UICONTROL 生成]**。


### 示例

假设您要跟踪用户在您的网站上最受欢迎页面之间切换的路径。

1. 创建如上所述的流量可视化图表。
1. 将&#x200B;[!UICONTROL **页面**]&#x200B;维度拖入&#x200B;**[!UICONTROL 包含]**&#x200B;字段中，然后选择&#x200B;[!UICONTROL **生成**]。
1. 流量可视化图表将构建，其中查看次数最多的页面位于可视化图表的中心，且位于焦点节点。 您还可以看到进入该页面的顶部页面（焦点节点的左侧）以及进入该页面的顶部页面（焦点节点的右侧）。
1. 分析流中的数据，如[配置](#configure)中所述。


## 配置

流量配置的摘要显示在可视化图表的顶部。 图表中的路径按比例显示。活动越多，路径越粗。

![显示以访问结束的流量输出示例，路径维度：页面，以及流量容器：访客。](assets/flow-output.png)

要进一步深入了解数据，您有几个选项：

* 流量图是交互式图表。将鼠标置于该图上可更改显示的详细信息。

* 选择图表中的节点时，将显示该节点的详细信息。再次选择节点以将其折叠。

  ![显示节点详细信息的交互流程图示例。](assets/node-details.png)

* 您可以通过筛选列仅显示某些结果，例如包括和排除、指定条件等。

* 选择左侧或右侧的![AddCircle](/help/assets/icons/AddCircle.svg)展开列。

* 若要自定义输出，请使用[上下文菜单](#context-menu)选项。

* 要编辑流或使用其他选项重建流，请选择配置摘要旁边的![编辑](/help/assets/icons/Edit.svg)。

## 筛选

当您将鼠标悬停在每列上方时，会出现一个筛选器![筛选器](/help/assets/icons/Filter.svg)。 通过选择过滤器，您将获得与自由格式表格中存在的相同的过滤器对话框。 查看[筛选和排序](freeform-table/../../freeform-table/filter-and-sort.md)。

* 使用&#x200B;**[!UICONTROL 显示高级]**&#x200B;配置高级设置以包含或排除包含运算符列表的特定条件。 有关详细信息，请参阅[筛选器和排序](../freeform-table/filter-and-sort.md)。
* 筛选列后，该特定列将反映筛选结果。 蓝色![筛选器](/help/assets/icons/FilterColored.svg)表示该列已筛选。  过滤器或者缩小列以仅显示过滤器中允许的项目。 或者，它会删除所有项目，但您希望筛选器中包含的项目除外。
* 只要有数据流入其余节点，所有下游和上游列都会保留。
* 要删除筛选器，请选择![筛选器](/help/assets/icons/Filter.svg)以打开筛选器菜单。 删除应用的任何过滤器，然后选择&#x200B;**[!UICONTROL 保存]**。流量应返回到其先前的未过滤状态。

## 上下文菜单

在流量可视化图表的任意节点上使用上下文菜单，这些菜单具有以下选项：

| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 关注此节点]** | 转而关注选定的节点。关注节点在流量图表的中间显示。 |
| **[!UICONTROL 从头开始]** | 返回到自由格式图生成器，您可从中生成新的流量图。 |
| **[!UICONTROL 为此路径创建筛选器]** | 创建过滤器。此选择将带您进入过滤器生成器，您可以在其中配置新过滤器。 |
| **[!UICONTROL 细分]** | 按可用维度、量度或时间分解节点。 |
| **[!UICONTROL 筛选列]** | 显示的过滤器选项与在自由格式表格中可用的选项相同。 有关可用选项的更多信息，请参阅[对表进行筛选和排序](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的“将简单或高级筛选器应用到表”一节。 |
| **[!UICONTROL 排除项]**&#x200B;或&#x200B;**[!UICONTROL 还原排除项]** | 从列中删除特定节点，并将其自动创建为列顶部的过滤器。若要还原排除项，请从上下文菜单中选择&#x200B;**[!UICONTROL 还原排除项]**。 您也可以打开列顶部的过滤器，移除带有您刚刚排除的项目的 Pillbox。 |
| **[!UICONTROL 趋势]** | 为节点创建趋势图表。 |
| **[!UICONTROL 显示下一列]** / **[!UICONTROL 显示上一列]** | 显示可视化图表的下一列（右）或上一列（左）。 |
| **[!UICONTROL 隐藏列]**n | 在可视化图表中隐藏选定的列。 |
| **[!UICONTROL 扩展整列]** | 扩展某一列以显示全部节点。默认情况下，只会显示头五个节点。 |
| **[!UICONTROL 从所选内容创建受众]** | 根据所选的列创建受众。 |
| **[!UICONTROL 折叠整列]** | 隐藏某一列中的所有节点。 |

## 限制到第一次/最后一次发生次数

使用此选项时，请记住：

* **[!UICONTROL 限制到第一次/最后一次发生次数]**&#x200B;仅统计序列中的第一次/最后一次发生次数。所有其他满足 **[!UICONTROL Starts with]** 或 **[!UICONTROL Ends with]** 标准的发生次数均会被弃用。
* 如果与&#x200B;**[!UICONTROL Starts with]**流量一起使用，则只包括与开始条件匹配的第一次发生次数。
在下面的示例中，在流程的每个步骤中包括**添加到购物车&#x200B;*和*产品主类别&#x200B;*的所有**次发生次数。*
  ![无限制，第一个](assets/limitofffirst.png)

  在下面的示例中，仅包括流程每个步骤中&#x200B;*添加到购物车*&#x200B;和&#x200B;*产品主类别*&#x200B;的&#x200B;**前**次发生次数。
  ![Lint，开始](assets/limitonfirst.png)
* 如果与&#x200B;**[!UICONTROL Ends with]**流量一起使用，则只包括与结束条件匹配的最后一次发生次数。
在下面的示例中，在流程的每个步骤中包括*产品主类别*&#x200B;和&#x200B;*添加到购物车*&#x200B;的所有&#x200B;**次发生次数。**
  ![无限制，第一个](assets/limitofflast.png)

  在下面的示例中，仅包括流程每个步骤中&#x200B;*产品主类别*&#x200B;和&#x200B;*添加到购物车*&#x200B;的&#x200B;**最后**次发生次数。
  ![Lint，开始](assets/limitonlast.png)
* 使用的系列因容器而异。如果使用&#x200B;**[!UICONTROL 人员]**&#x200B;容器，则一系列事件是会话。 如果使用&#x200B;**[!UICONTROL 会话]**&#x200B;容器，则事件系列是给定用户在提供的日期范围内的所有事件。
* 在&#x200B;**[!UICONTROL Starts with]**&#x200B;或&#x200B;**[!UICONTROL Ends with]**&#x200B;字段中使用指标或Dimension项时，可以在高级设置中配置&#x200B;**[!UICONTROL 限制到第一次/最后一次发生次数]**&#x200B;选项。


>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


<!--
## Create a flow visualization {#configure}

1. Add a blank panel to your project and click the visualizations icon in the left rail. 

   Or
   
   Add a visualization in any of the ways described in the "Add visualizations to a panel" section in [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Anchor your Flow visualization using one of the following options:

   * [!UICONTROL **Starts with**] (metrics, dimensions, or items), or
   * [!UICONTROL **Contains**] (dimensions, or items), or
   * [!UICONTROL **Ends with**] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." You can populate the drop zone in 3 ways:

   * Use the drop-down menu to select metrics or dimensions.
   * Drag dimensions or metrics from the left rail.
   * Begin typing the name of a dimension or metric, then select it when it appears in the drop-down list.

   >[!IMPORTANT]
   >
   >Calculated metrics cannot be used in the  **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.

1. If you choose a metric, you also need to provide a [!UICONTROL **Pathing Dimension**] to use as your path leading to or coming from your selected component, as shown here. The default is [!UICONTROL **Page**].

   ![pathing dimension](assets/pathing-dim.png)

1. (Optional) Select **[!UICONTROL Show advanced settings]** to configure any of the following options:

   ![advanced settings](assets/adv-settings.png)

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. <p>This option is disabled by default.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to those that start/end with the first/last occurrence of a dimension/item/metric. See the section below, [Example scenario for 'limit to first/last occurrence'](#example-scenario-for-limit-to-firstlast-occurrence), for a more detailed explanation. |
   | **[!UICONTROL Number of columns]** | The number of columns you want in your Flow diagram. You can specify a maximum of 5 columns. |
   | **[!UICONTROL Items expanded per column]** | The number of items you want in each column. You can specify a maximum of 10 items expanded per column.  |
   | **[!UICONTROL Flow container]** | <ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.|

   >[!IMPORTANT]
   >
   >The combination of **[!UICONTROL Number of columns]** and **[!UICONTROL Items expanded per column]** determine the number of underlying requests required to create the flow visualization. The higher those numbers, the longer it takes to render a visualization.

1. Select **[!UICONTROL Build]**.

>[!INFO]
>
>**Example:** Suppose that you want to trace the path that users took both to and from the most popular pages on your site.
>
>To do this, you would
> 
>1. Begin creating a flow visualization as described above.
>1. Drag the [!UICONTROL **Page**] dimension into the **[!UICONTROL Contains]** field, then select [!UICONTROL **Build**].
>1. The Flow visualization builds with the most-viewed page visible in the focus node in the center of the visualization. You also see the top pages leading into that page (to the left of the focus node) as well as the top pages leading out of that page (to the right of the focus node).
>1. Analyze data in the flow, as described in [View and change the Flow output](#view-and-change-the-flow-output).


## View and change the Flow output {#output}

![flow output](assets/flow-output.png)

A summary of the Flow configuration appears at the top of the diagram. The thickness of a path in the diagram is proportional to its activity, with paths with more activity appearing thicker than those with less activity.

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you select on a node in the diagram, the details for that node appear. Select on the node again to collapse it.

   ![node-details](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, and so forth.

* Select the plus sign (+) on the left to expand a column.

* Use the right-click options explained below to further customize the output.

* Select the pencil icon next to the configuration summary to further edit the flow or rebuild it with different options.

* You can also export and further analyze your Flow diagram as part of a project's .CSV file by going to **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtering

Above each column, a filter appears when you hover over it. By selecting the filter, you get the same filter dialog that exists in the Freeform table today. This filter works the same as it does in the Freeform table.

* Use advanced settings to include or exclude certain criteria with our list of operators.
* Once you have filtered an item from the list, that specific column will reflect the filtering. (The filter either reduces it to only show the item allowed in the filter, or it removes all items except for the one item you want in the filter.
* All downstream and upstream columns should persist, as long as there is data flowing into the remaining nodes.
* Once applied, the filter icon appears in blue above the column it is filtering.
* To remove a filter, select the filter icon to open the filter menu. Remove any filters applied and then select **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Right-click options {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Start over] | Returns you to the Freeform diagram builder, where you can build a new Flow diagram. |
| [!UICONTROL Create segment for this path] | Create a segment. This takes you into the Segment Builder, where you can configure the new segment. |
| [!UICONTROL Breakdown] | Break the node down by available Dimensions, Metrics, or Time. |
| [!UICONTROL Trend] | Create a trended diagram for the node. |
| Show next column / Show previous column | Reveals the next (right) or previous (left) column of the visualization. |
| Hide column | Hides the selected column from the visualization. | 
| [!UICONTROL Expand entire column] | Expand a column to show all nodes. By default, only the top five nodes display. |

## Example scenario for 'limit to first/last occurrence'

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded.
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included.
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria will be included.
* The series used differs based on the container. If using the **[!UICONTROL Visit]** container, the series of hits will be the session. If using the **[!UICONTROL Visitor]** container, the series of hits will be all the hits for a given user in the provided date range.
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the "Starts with" or "Ends with" fields.

Example series of hits:

Home > Products > Add to cart > Products > Add to Cart > Billing > Order Confirmation

### Consider a flow analysis using the following settings:

* Start with[!UICONTROL  Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits counts 2 occurrences of "Add to Cart".
Expected Flow Output:
"Add to Cart" (2) —> "Products" (1)
                  -> "Billing" (1)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the first occurrence of "Add to cart" is included in the analysis.
Expected Flow Output:
"Add to Cart" (1) —> "Products" (1)

### Consider the same series of hits but using the following settings:

* Ends with [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of hits would count 2 occurrences of "Add to Cart".
Expected Flow Output:
"Products" (2) <— "Add to cart" (2)

However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the last occurrence of [!UICONTROL Add to cart] would be included in the analysis.
Expected Flow Output:
"Products" (1) <— "Add to cart" (1)

-->