---
description: 'null'
title: 配置流失可视化
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 2cd9872ed5052b9569d03a07d5171221b9e0af29

---


# 配置流失可视化

您可以指定触点以创建多维流失序列。 通常，触点是站点上的页面。 但是，接触点不仅限于页面。 例如，您可以添加事件（如单位），以及唯一访客和回访。 您还可以添加维，如类别、浏览器类型或内部搜索词。

您甚至可以在接触点内添加区段。 例如，您可能希望比较区段，如iOS和Android用户。 将所需的区段拖动到流失的顶部，这些区段的相关信息会添加到流失报告中。 如果只显示这些区段，可以删除所有访问基准。

对于可添加的步骤数或使用的维数，没有限制。

您可以在eVar上执行路径分析，包括销售eVar和 [listVar](https://marketing.adobe.com/resources/help/zh_CN/sc/implement/listN.html) (每次点击可具有多个值的变量，如产品、listVar、销售eVar和列表prop)。 例如，假设某个用户在一个页面上查看鞋和衬衫，而在另一个页面上查看衬衫和袜子。下一份关于鞋类产品流量的报告是衬衫和袜子，而不是衬衫。

1. 将可 [!UICONTROL Fallout] 视化下拉菜单中的可视化拖入 [!UICONTROL Freeform Table]。

1. Drag the Page dimension into the Freeform Table and from there, drag a page (in this case, Home - JJEsquire) into the **[!UICONTROL Add TouchPoint]** field as the first touchpoint.

   ![](assets/fallout1.png)

   将鼠标悬停在某个接触点上会看到流失和与该级别有关的其他信息，如接触点的名称、该接触点的访客数，同时还可以看到该接触点的成功率（以及将成功率与其他接触点进行比较）。

   条形灰色部分中的圆圈数字显示接触点之间的流失情况（而非到该点的整体流失情况）。 接触点%显示从上一步到流失报表中当前步骤的成功流失。

   您还可以向流失报表中添加单个页面，而不是整个维度。 单击页面维度上的向右箭头“>”以选择要添加到流失报表的特定页面。

1. 继续添加触点，直到序列完成。

   通过将 **一个或多个其他接触点拖动到接触点** ，可以组合多个接触点。

   >[!NOTE]
   >
   >多个区段通过 AND 相连，而多个项目（如维度项目）和量度通过 OR 相连。

   ![](assets/multiple_obj_touchpoint.png)

1. You can also **constrain individual touchpoints to the next hit** (as opposed to &quot;eventually&quot;) within the path. 在每个接触点下方都有一个选择器，其中包含选项“最终路径”和“下一次点击”，如下所示：

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>最终路径 </p> <p>(默认) </p> </td> 
   <td colname="col2"> <p>访客数量会“最终”登陆路径的下一页，但不一定在下一次点击时。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>下一次点击 </p> </td> 
   <td colname="col2"> <p>访客会被计数，它将在下一次点击的路径下一页。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 流失设置 {#section_0C7C89D72F0B4D6EB467F278AC979093}

| 设置 | 描述 |
|--- |--- |
| 流失容器 <ul><li>访问</li><li>Visitor</li></ul> | 用于在“访问”和“访客”之间切换以分析访客路径。默认值为“访客”。这些设置可帮助您在访客级别（跨访问）了解访客参与程度，或将分析限定于单次访问。 |
| 显示“所有访客”作为第一个接触点。 | 如果不希望将“所有访客”作为第一个接触点，您可以取消选择此设置。 |

当您&#x200B;**右键单击某个接触点**&#x200B;时，将会显示以下选项：

| 选项 | 描述 |
|--- |--- |
| 趋势接触点 | 在线图中查看接触点的趋势数据，包括一些预建的异常检测数据。 |
| 趋势接触点(%) | 趋势化总流失百分比。 |
| 趋势化所有接触点(%) | 将流失中的所有接触点百分比趋势化（“所有访问”除外，如果包括），则显示在同一图表上。 |
| 在此接触点划分落差 | 视图两个接触点（此接触点和下一个接触点）之间的访客行为（如果它们继续到下一个接触点）。 这将创建一个自由形式表，其中显示您的尺寸。 可替换表的尺寸和其他元素。 |
| 在此接触点细分流失 | 视图未通过漏斗的人员在选择步骤后立即执行的操作。 |
| 从接触点创建区段 | 从选定的接触点创建新区段。 |
