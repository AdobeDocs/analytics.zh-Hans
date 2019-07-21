---
description: 配置整体行为设置。例如，您可以配置自动保存、图表和表设置，以及指定字体和区域设置。
seo-description: 配置整体行为设置。例如，您可以配置自动保存、图表和表设置，以及指定字体和区域设置。
seo-title: 设置
title: 设置
uuid: 34444052-479b-4923-b379-a03 ca614 bf3 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 设置

配置整体行为设置。例如，您可以配置自动保存、图表和表设置，以及指定字体和区域设置。

## 设置 {#concept_D21E3D6F13EA4F97913F60C243B72173}

配置整体行为设置。例如，您可以配置自动保存、图表和表设置，以及指定字体和区域设置。

Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Settings]** to access [!UICONTROL Global Settings].

## “常规设置”选项卡 - 定义{#reference_EADAF83466994F89BCC6B0F49A9A53DB}

为数据源、项目保存、图表和表格配置行为设置。

<!-- 

r_dsc_general_settings.xml

 -->

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字段 </p> </th> 
   <th colname="col2" class="entry"> <p>定义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 数据设置 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">计算重复实例</span>：指定是否在报表中计算实例。这意味着，如果您针对相同的变量具有多个序列值，则可以将它们计为该变量的一个实例，也可以计为多个实例。 </p> <p>例如，您可能会看到重复的页面重新加载，这是在单次访问期间您的网站上页面重新加载或刷新的次数。通过使用此选项，您可以指定是将相同页面上的多次点击计为一次页面查看，还是计为多次页面查看。 </p> <p> <span class="uicontrol"> <span class="keyword">Ad hoc Analysis</span></span>：指定“<span class="keyword">Ad hoc Analysis</span>”为报表的唯一数据源。此数据来自网页生成的图像请求。 </p> <p> <span class="uicontrol"><span class="keyword">数据源</span></span>：指定是否使用从其他 Adobe 资源或自定义数据源上传的数据。此数据可用于 <span class="keyword">Experience Cloud</span> 中的产品。请参阅<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html" scope="external" format="html">数据源</a>以了解详细信息。 </p> <p> <span class="uicontrol">两者皆有</span>：（默认）使用来自“<span class="keyword">Ad Hoc Analysis</span>”和其他数据源的数据。 </p> <p>注意：改变这些选项可能造成 <span class="keyword">Ad Hoc Analysis</span> 数据和 <span class="keyword">Marketing Reports &amp; Analytics 数据</span>之间出现差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自动保存设置 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">启用自动保存</span>：启动自动保存功能。 </p> <p> <span class="uicontrol">自动保存项目频率</span>：用于调整自动保存功能的时间增量。仅在 Ad hoc Analysis 崩溃时自动保存项目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 图表设置 </p> </td> 
   <td colname="col2"> <p><b>默认情况下折叠图表</b>：单击此按钮可显示隐藏了顶部图表的报表。如果使用此选项显示报表，您可以采取手动的方式展开顶部图表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 表设置 </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol">显示行编号</span>：在报表中打开或关闭行编号。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## “排名”选项卡 - 定义{#reference_FB9BADD7E3DA42C1BB2A02A6E9D5C1CF}

配置数据在列中的显示方式，并为流量和转化报表选择默认量度。

<!-- 

r_dsc_ranked_tab.xml

 -->

| 字段 | 定义 |
|--- |--- |
| 列设置 | 配置如何在表中显示单元格数据，以及图表中的条形图。 |
| 选择默认量度 | 除了可用于所有报表的量度以外，还可为流量和转换报表指定默认量度。包含报表特定的默认设置：指明自定义视图时是否包含默认量度。 |

## “网站分析”选项卡 - 定义{#reference_9DD37C8EF718409E990E149596282FF8}

为网站分析报表配置量度和其他图形设置。

<!-- 

r_dsc_site_analysis_tab.xml

 -->

| 字段 | 定义 |
|--- |--- |
| 量度 | 选择柱体宽度和柱体高度表示的量度。确定要使用颜色显示的量度，并确定表示该量度的低值和高值的颜色。您可以构建 X 和 Y 轴的量度，并可添加任何希望在报表弹出文本中显示的其他量度。您也可反转显示的任何所选量度。 |
| 一般和警报 | 启用和禁用报表的特定图形元素。您可以配置警报，当与柱体所表示的页面相关联的量度传递特定值时，显示在报表中。 |

## “字体和区域设置”选项卡 - 定义{#reference_5F2129B67CC44E5BA9EA7E30A35BFB49}

指定语言的区域设置及默认字体。必须重新启动，字体和区域设置更改才能生效。

<!-- 

r_dsc_font_locale.xml

 -->

| 字段 | 定义 |
|--- |--- |
| 选择区域设置 | 指定用户界面的显示语言。 |
| 选择字体 | 用于指定要显示的字体。 |