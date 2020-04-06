---
description: 运行不同的报表类型的步骤。
title: 运行不同的报表类型
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 运行不同的报表类型

运行不同的报表类型的步骤。


## 运行排名报表 {#task_C570BA4A213F4F2EB7B30E012934BE7D}

在排名报表中，该表格根据数量或百分比显示报表页面与指标的相关排名。 排名报表可以在一份报表中显示多个量度。

<!-- 

t_reports_ranked.xml

 -->

1. 生成报表，如 [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**)。
1. In the report header, click **[!UICONTROL Ranked.]**
1.  要对报表排名，单击表格的列标题。

   排名报表的表格可列出最多 200 个项目（如产品、类别、网页等）以及十个量度（如收入、订购、查看次数等）。

## 运行趋势报表 {#task_F03B4E760B9E4EA29FC3F654E6316887}

趋势报表显示一段时间内的指标。 当您想要了解区段从一个时间段到下一个时间段的表现时，可使用此报告类型。

<!-- 

t_reports_trended.xml

 -->

大多数“转化”和“流量”报表都提供“趋势视图”。 使用 [!UICONTROL Calendar]该功能，您可以显示任何时段细分的改进，包括一个月的天数、一年的周数、季度的周数、一年的月数等。 趋势报表显示单个指标(收入、订单、视图等)的趋势(最多五个项目，如产品、类别、网页等)。

**运行趋势报表**

1. 运行转化或流量报告，如 **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**。
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## 运行转化漏斗报表 {#task_B926A74AA6A641138C2986C1635120CB}

“转换漏斗”报表显示经过一组访客以执行所需操作的事件百分比。 例如，您可以查看有多少访客从访问网页到向购物车添加物品，再到购买物品的过程。 此报告还显示了在途中流失的人数。

<!-- 

t_reports_conversion_funnel.xml

 -->

要运行此报表，请选择一个报表，如页面报表( **[!UICONTROL Reports]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** > **[!UICONTROL Campaign Conversion Funnel]**)。

有关描述，请参阅[转化报表](https://marketing.adobe.com/resources/help/zh_CN/reference/reports_conversion.html)。

## 运行流失报表 {#task_8FD97C8260464F9DA731A93DB8F80184}

显 [!UICONTROL Fallout Report] 示访问预先指定的页面序列的访客数。 它还显示了每个步骤之间的转化率和流失率。

<!-- 

t_reports_fallout.xml

 -->

查看分析工作区 [中新的](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/fallout_flow.html) “流失”分析面板！

1. 在中， [!UICONTROL Adobe Analytics]单击 **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**。
1. 在页面 [!UICONTROL Fallout Report] 上，单击 **[!UICONTROL Launch the Fallout Report Builder]**。

   ![步骤结果](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. 单击 **[!UICONTROL Run Report]**.

   ![步骤结果](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [流失报表描述](https://marketing.adobe.com/resources/help/zh_CN/reference/reports_fallout.html)


## 运行页面流量报表 {#task_133E8B87C3F04DA0A42D10CBA499305B}

“页面流量”报表显示访客访问页面和在站点中导航的顺序。 此报告有助于回答

查看分析工作区 [中新的](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/flow.html) “流”可视化！

运行路 [径报](https://marketing.adobe.com/resources/help/zh_CN/reference/reports_paths.html) 告。

例如，单击 **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**。

![](assets/page_flow.png)

您从左至右阅读此报告，从所选页面开始。 在选定页面后查看的页面以向右扩展的分支形式显示。

随后查看的每个页面的百分比显示在页面名称旁边。 连接到每个下一页的线条的宽度描绘了此相对百分比。

**[!UICONTROL Path Views]**:指示在限制为显示的路径时查看页面的次数。

例如，“隐私政策”页面的总页面视图数可能为10,000，但仅有500个页面视图数在主页后立即发生。 因此，使用术语路径视图。

线的相对宽度描绘了相对百分比。 默认情况下，此报告显示5个2级分支和5个3级分支。您可以将分支数量增加到最多十个2级分支和5个3级分支。 这样做会增加报表的高度，并且极有可能需要滚动以视图整个图形。

## 运行漏斗报表 {#task_2BBF6FACD48F479E8B2EE458919941CB}

您可以选择成功事件，并将其添加到 [!UICONTROL Purchase Conversion Funnel] 报表或报 [!UICONTROL Product Conversion Funnel] 表。

<!-- 

t_reports_funnel.xml

 -->

1. 单击 **[!UICONTROL Reports]** > **[!UICONTROL Products]** >产 [品转换漏斗](https://marketing.adobe.com/resources/help/zh_CN/reference/reports_conversion_funnel.html)。

## 运行营销渠道报表 {#task_64ADED5CC75248319E06E3E029B47F78}

营销渠道报告提供第一次和最后一次接触渠道分配的概述报告，其中包含标准报告指标，如收入、订单和成本。 这些报表使您能够分析每个渠道所产生的收入。

<!-- 

t_reports_marketing_channel.xml

 -->

See the [Marketing Channel](https://marketing.adobe.com/resources/help/zh_CN/mchannel/index.html) help system for more information.

## 运行异常检测报表 {#task_4808C96327354D789C075823F5C3A049}

描述如何解读异常检测中的概要图表和各个量度图表。

<!-- 

t_anomaly_view.xml

 -->

在 Analysis Workspace 中查看新的[异常检测和贡献分析](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/anomaly_detection.html)功能！

**[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Anomaly Detection]** .

>[!NOTE] 另外，您也可以在 Analysis Workspace 项目中运行异常检测。[更多...](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/anomaly_detection.html)

有关设置异常检测的信息，请参阅《参考 [指南》](https://marketing.adobe.com/resources/help/zh_CN/sc/user/index.html#Setting_up_Anomaly_Detection)。

异常检测显示两种类型的图表：摘要图表和各个指标图表。 仅当检测到该量度至少有一个异常时，才会显示单个量度图表。

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>图表类型 </p> </th> 
   <th colname="col2" class="entry"> <p>什么是 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>摘要图表 </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">每个框代表每天跟踪的一个异常，该异常与下面的一个指标对应。 </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">绿色表示异常高于趋势线，蓝色表示异常低于趋势线。 </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">指示异常的强度：异常越大，数据点的颜色越深，距离趋势线越远。 </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">单击单个异常会将该异常的单个度量图表（在摘要图表下）带到顶部。 </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">偏差百分比值（图表左侧）的计算如下： 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">如果上界和期望值相同，则偏差%为100% </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">否则，偏差百分比为：((实际值 – 上限值) / (上限值 – 期望值)) * 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">如果下限与期望值相同，则偏差百分比为 -100%。 </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">否则，偏差百分比为：((下限值 – 实际值) / (期望值 – 下限值)) * -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">单击<span class="uicontrol">显示区段</span>可显示区段边栏，以允许您将区段应用到异常检测报表。请参阅有关分段的<a href="https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/"  >更多信息</a>。 </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">单击<span class="uicontrol">编辑量度</span>可让您选择和取消选择要为其检测异常的量度。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单个量度图表 </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">将各个趋势度量（包括计算度量）的异常数据点显示为点。 </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">在顶部显示最近的异常，并按异常数次次排列。 </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">显示一个实线，以指示当前收集的实际数据。 将其与预测和误差裕度进行比较以导出数据点是否异常。 </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">显示虚线，该虚线基于历史数据（即培训期）表示预测。 </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">在灰色阴影中显示95%置信度的上限和下限。 </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">允许您通过单击度量名称旁的多次向上或向下箭头来折叠和展开单个报表。 </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">通过对概述报告中的下钻进行反应来更改度量图表的显示顺序（请参阅上文） </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">允许您使用搜索词（如所有与页面相关的度量的“页面”）筛选图表。 </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">允许您显示您定义的所有指标或仅显示具有异常的指标。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置异常检测 {#task_AF347B34F56E44A6AE70E019B6EB2F08}

选择报表包、量度和培训/查看时段以便进行异常检测的步骤。

<!-- 

t_anomaly_config.xml

 -->

您可以为每个报表包单独设置异常检测。

1. 导航到 **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** 。
1. 选择要跟踪每日异常检测情况的报表包。要显示报表包列表，请单击“报表包”选择器下拉菜单。
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]** at the top right of the screen:  ![](assets/metrics_icon.png).

   您可以从以下位置选取量度：所有量度的列表（包括计算量度）或跟踪量度的列表。您还可以依据特定词语进行过滤，以缩小列表范围。1. Once the report has been generated, define the **[!UICONTROL Training Period]** and the **[!UICONTROL View Period]** for anomaly detection. （将培训时段看作是算法的“学习时段”。）

   ![](assets/view_training_periods.png)

   请记住以下事项：

* 培训期在视图期开始之前结束。
* 两者的默认值均为30天，您可以将其延长到60或90天。
* 延长培训期可让您的数据处于更大的上下文中，并可能会减少异常的大小。

   每次您更改参数时，异常检测量度报告都会刷新。
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   有关创建和管理区段的详细信息，请参阅《[Analytics 分段指南](https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/)》。1. （可选）将报表加入收藏夹或为其添加书签。
1. （可选）更改查看时段的结束日期。默认日期为昨天。
1. 您现在可以开始解读报表了。[查看异常检测图表](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049)。

## 运行实时报表 {#task_5D25929C918E40B18965222FA94176B0}

描述如何查看和解读实时报表。

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]**。

实时报告优惠两个主要报表——概述报表和详细报表。 每个报告都包含许多缩图报告。

有关配置实时报告的信息，请参阅《分析参 [考指南》](https://marketing.adobe.com/resources/help/zh_CN/reference/index.html#RealTime_Reports_Configuration)。

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> UI组件 </th> 
   <th class="chdeschd"> 描述 </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>选择报表包</strong></td> 
   <td class="chdesc stentry"> 显示此实时报表涵盖的报表包。要更改报表包，请参阅<a href="https://marketing.adobe.com/resources/help/zh_CN/reference/t_realtime_admin.html"  >实时报表配置</a>。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>切换报表</strong></td> 
   <td class="chdesc stentry"> 您可以在设置的报表（最多 3 个）间切换。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>选择时间范围</strong></td> 
   <td class="chdesc stentry"> 您可以选择报表中的所有缩图报表使用的整体时间范围。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>配置报表</strong></td> 
   <td class="chdesc stentry"> 仅当您具备管理员权限时，才能看到这个齿轮图标链接。单击该链接可访问位于<span class="ignoretag"><span class="uicontrol">管理工具</span> &gt; <span class="uicontrol">报表包</span> &gt; <span class="uicontrol">编辑设置</span> &gt; <span class="uicontrol">实时</span></span>中的报表包管理器。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>全屏视图</strong></td> 
   <td class="chdesc stentry"> 仅当您的显示器具有特定的纵横比（16:9 或 16:10）并且浏览器对此提供支持时，才能看到全屏视图图标。请注意，当屏幕处于全屏模式时，您无法与屏幕进行交互（按 <span class="uicontrol">Esc</span> 可退出）。全屏模式不涉及超时。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>网站流量缩图报表</strong></td> 
   <td class="chdesc stentry"> 蓝色趋势线数据显示整个站点的总流量。 X轴使用文本标签（15分钟前，10分钟前），但当前值除外，它显示为实时表达式。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>网站总计缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示最近N分钟内实时报告所选量度的站点总数。 “N”可通过“时间范围”选择器进行配置。 <p>箭头的颜色和方向基于以下算法： 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">显着增益（向上箭头）:&gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">增益（向上箭头）:5%到100%之间 </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> 平面（向右箭头）:5%到-5%之间 </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> 丢失（向右下箭头）:-5%到-100%之间 </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> 重大损失（向下箭头）:&lt; -100% </li> 
      </ul> </p> <p>如果在“实例”中报告站点总数，则这些实例反映主缩图报表中的维度。 如果存在特定于实例的名称(如“页面视图”)，则站点总计会报告该名称。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>主要缩图报表</strong></td> 
   <td class="chdesc stentry"> 实时报表的主要维度及其度量的报表。 显示所选时间范围内该元素的趋势线。 度量总计表示完整趋势线的总和。 箭头指示项目是强增、增、平、减还是强减。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>搜索对话框</strong></td> 
   <td class="chdesc stentry"> 搜索会影响所有缩图报表。 在视图报表时，搜索会持续存在。 </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>按最受欢迎/获胜方/失败方进行排序</strong></td> 
   <td class="chdesc stentry"> 您可以按<span class="uicontrol">最受欢迎</span>（默认）、<span class="uicontrol">获胜方</span>（显示增长最多的维度）和<span class="uicontrol">失败方</span>（处于下跌轨迹的维度）切换排序。 <p>下面是用来确定获胜方或失败方的公式：“实时”查看最早的示例和接近最新的示例，然后执行简单的“% 变更”计算。如果选定“最近 15 分钟”，且 n 代表当前时间，则会计算 n-1 与 n-15 期间的变更情况。Real-Time目前没有任何权重。 忽略当前分钟数，因为它不完整，并且可能会产生错误的%更改。 </p> <p>此公式在实时报告中使用的所有指标上都保持一致。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 1 缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示第二个配置报表的维度和度量的实时报表。 <p>第1次报告显示前4位类别;第5个是所有剩余值的汇总。 对于每个类别，提供该类别的总原始视图。 此外，所有类别的总数显示在中心。 </p> <p> 将鼠标悬停在某个部分上会突出显示关联的类别，并在圆环下方显示类别趋势线。 </p> <p> 将鼠标悬停在行项目上可突出显示行项目以及关联的部分，并在圆环下方显示类别趋势线。 </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>次要 2 缩图报表</strong></td> 
   <td class="chdesc stentry"> 显示第三个配置报表的维度和度量的实时报表。 将鼠标悬停在项目标签顶部会将标签滑向右侧，并显示悬停项目的趋势线。 </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **项目趋势缩图报表** | 显示在“概述”报告中选择的项目在最近N分钟内的趋势线。 N可通过时间范围选择器进行配置。 |
   |---|---|
   | **项目总计缩图报表** | 显示在概述报告中选定的项目在最近N分钟内的总量度计数。 N可通过时间范围选择器进行配置。 |
   | **关联的二级报表1** | 此缩图报表与第1次缩图报表非常相似。 唯一的区别是用于填充此报表的数据源：在此示例中，它显示特定页面（在概述报告的主缩图报告中选择的页面）与查看的实例之间的关联（或划分）。 |
   | **关联的二级报表** | 此缩图报表与第2次缩图报表非常相似。 唯一的区别是用于填充此报表的数据源：在此示例中，它显示特定页面（在概述报表的主缩图报表中选择的页面）与语言维度之间的关联（或划分）。 |
