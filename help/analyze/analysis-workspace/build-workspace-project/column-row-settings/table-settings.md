---
description: 行设置因您拖入到表格中的组件而异。
seo-description: 行设置因您拖入到表格中的组件而异。
seo-title: 行设置
title: 行设置
uuid: f30c31d5-1fd4-4b93-94c3-ca441099 fe2 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 行设置

行设置因您拖入到表格中的组件而异。

您还可以[在表格中使用右键单击操作](../../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F)来管理选定行。

要访问表格行设置，请单击每个行内的维度、区段、量度、时间段或划分旁边的“设置”图标：

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 行设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> 日期比较</a> </p> </td> 
   <td colname="col2"> <p><b>将每列的日期调整为全部从同一行开始。</b> </p> <p>如果选择调整日期，例如在 2016 年 10 月和 9 月间的月同比比较中，左列将从 10 月 1 日开始，右列将从 9 月 1 日开始： </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>默认情况下处于禁用状态。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>百分数 </p> </td> 
   <td colname="col2"> <p><b>按行计算百分比</b> </p> <p>强制自由格式表按行计算单元格百分比，而不是沿列计算。这对显示百分比趋势特别有用。在使用<span class="uicontrol">可视化</span>图标时，默认情况下会开启该设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列总计 </p> </td> 
   <td colname="col2"> <p>这些设置只显示<a href="../../../../analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md#concept_C50E7DFBC0504C72A973123192F487D8" format="dita" scope="local">手动（静态）行</a>（在选择了有限项目集时），而不显示动态行（在显示所有项目的维度中拖放时）。 <p>注意：对于<i></i>“量度”手动行，该设置处于禁用状态，因为对表格中当前行以外的任何量度进行汇总都是毫无意义的。 </p> </p> <p><b>通过汇总当前每列的值来计算总数（默认情况下处于启用状态）：</b> </p> <p>此选项仅计算表格中的当前行。（客户端计算） </p> <p><b>根据每个量度的所有行计算总数（默认情况下处于禁用状态）：</b> </p> <p>此选项包括此维度的所有维度项目，甚至包括未列在表格中的维度项目。（服务器端计算） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>划分 </p> </td> 
   <td colname="col2"> <p><b>按位置划分：</b> </p> <p>您可以基于自由格式表中的固定位置执行划分。例如，您可以指定始终对表的头七行进行划分。 </p> <p>（以前，划分中的值列表会被“锁定”。这会导致这样一种情况，例如，如果您按<span class="term">页面</span>划分<span class="term">日期</span>，则会得到您选定日期范围内头 50 页的列表。如果您保存了该报表然后在一个月后运行它，则头 50 页很可能已发生更改。然而，Analysis Workspace 将使用来自原始划分的结果并返回相同页面，但将当前月份作为日期范围。） </p> <p>要执行基于固定位置的划分，请执行以下操作： </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">划分表格中的一些行。 </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">单击希望处于固定位置的表格行旁边的“设置”（齿轮）图标。 </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">选中<span class="uicontrol">按位置划分</span>旁边的复选框。 </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">更改排序顺序或日期范围，并注意划分现在已绑定到行位置，而不是硬编码的行。 </li> 
    </ol> <p>默认情况下处于禁用状态。 </p> </td> 
  </tr> 
 </tbody> 
</table>

