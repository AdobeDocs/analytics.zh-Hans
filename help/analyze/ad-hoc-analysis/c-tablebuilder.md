---
description: 可以使用表生成器创建具有任何量度、维度、区段配置的报表。例如，您可以将多个量度添加到表生成器中，然后将区段同时应用于所有量度。您可以从工具窗格中将项目应用为行和划分，或者应用为列，然后轻松旋转表以获得不同的视图。在生成表后，您可以直接与结果数据表交互以进行进一步分析。请记住，从表生成器中生成数据表时会运行查询和创建新的数据表。
seo-description: 可以使用表生成器创建具有任何量度、维度、区段配置的报表。例如，您可以将多个量度添加到表生成器中，然后将区段同时应用于所有量度。您可以从工具窗格中将项目应用为行和划分，或者应用为列，然后轻松旋转表以获得不同的视图。在生成表后，您可以直接与结果数据表交互以进行进一步分析。请记住，从表生成器中生成数据表时会运行查询和创建新的数据表。
seo-title: 表生成器
title: 表生成器
uuid: d5dbd05e-9ebd-4571-b3 a5-3856c28 b65 f3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 表生成器

可以使用表生成器创建具有任何量度、维度、区段配置的报表。例如，您可以将多个量度添加到表生成器中，然后将区段同时应用于所有量度。您可以从工具窗格中将项目应用为行和划分，或者应用为列，然后轻松旋转表以获得不同的视图。在生成表后，您可以直接与结果数据表交互以进行进一步分析。请记住，从表生成器中生成数据表时会运行查询和创建新的数据表。

## 表生成器 {#concept_574FEDC73B244101935D3C86C39DB70F}

可以使用表生成器创建具有任何量度、维度、区段配置的报表。例如，您可以将多个量度添加到表生成器中，然后将区段同时应用于所有量度。您可以从工具窗格中将项目应用为行和划分，或者应用为列，然后轻松旋转表以获得不同的视图。在生成表后，您可以直接与结果数据表交互以进行进一步分析。请记住，从表生成器中生成数据表时会运行查询和创建新的数据表。

[!UICONTROL 表生成器]不适用于特定路径报表，例如[!UICONTROL 网站分析]、[!UICONTROL 流失]、[!UICONTROL 流量]和[!UICONTROL 虚拟焦点]报表。

## 表生成器说明 {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 行/划分</span> </td> 
   <td colname="col2"> <p>从已添加的项目创建行和划分。您拖到<span class="wintitle">行/划分</span>的第一个项目将出现在数据表的左列，或者是划分中的父项目。添加后续项目以创建划分。 </p> <p>例如，如果您添加了页面和城市维度，则报表将按城市划分页面。您可以使用以下菜单来配置每个项目显示多少行和划分： </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol">显示</span>和<span class="uicontrol">划分</span>：用于指定要显示的项目和划分数目。 </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol">默认</span>：使用在<span class="wintitle">“划分属性”</span>中配置的设置。 </li> 
    </ul> <p>例如，您也可以配置固定值列表来按多个量度划分一个量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 划分属性</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>用于指定显示多少行和划分（根据您添加项目的顺序）的默认设置。您可以指定每页显示多少总结果，以及多少行要进行划分。 </p> <p>您在<span class="wintitle">表生成器</span>中的设置优先于<span class="wintitle">划分属性</span>中的默认设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 编辑项目</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>选择维度项目列表以针对划分创建一个固定列表。当您将项目添加到该列表时，它们会在保存的报表中持续存在，并且在打开保存的报表或计划报表时不会折叠。 </p> <p>请参阅 <a href="../../analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841" format="dita" scope="local"> 划分表格数据</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 列</span> </td> 
   <td colname="col2"> <p>用于通过维度、区段和量度项目生成列。您还可以使用旋转 X 和 Y 轴的箭头图标旋转各列。 </p> <p> <span class="uicontrol">显示</span>：用于限制在数据表中生成的列数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 概要</span> </td> 
   <td colname="col2"> <p>显示报表的结构布局，以便您了解将创建多少行和列。此摘要反映出<span class="uicontrol"></span>“行/划分”和“列”<span class="uicontrol"></span>组中指定的配置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 替换表</span> </td> 
   <td colname="col2"> <p>根据您的<span class="wintitle">表生成器</span>配置生成（和覆盖）现有表。 </p> <p>注意：单击“替换表”<span class="uicontrol"></span>会返回报表并覆盖表网格中的数据。如果您向表网格中添加项目，则表和<span class="wintitle">表生成器</span>之间的关联将失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 警告 </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>表示<span class="wintitle">表生成器</span>的配置将不会返回数据，或者未选择任何量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 从表生成器{#task_B04801AC9848485C93DF02E96C9A9902}中生成报表 

描述如何使用[!UICONTROL 表生成器]的步骤。

<!-- 

t_table_builder.xml

 -->

1. To access the [!UICONTROL Table Builder], run a supported report, then click **[!UICONTROL Table Builder]**.
1. 将工具窗格中的项目（维度、量度和区段）拖到[!UICONTROL 表生成器]中。
1. 将项目配置为行、划分和列。
1. Click **[!UICONTROL Replace Table]** to generate the report.

   在单击“替换表”**时，将运行新查询并创建新数据表。**&#x200B;不会在表生成器中反映对明细表的手动编辑。

