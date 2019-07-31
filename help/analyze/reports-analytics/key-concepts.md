---
description: 此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。
seo-description: 此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。
seo-title: Adobe Analytics-关键概念
title: Adobe Analytics-关键概念
uuid: ef5701c5-2d3e-4847-851f-9312d55db1a8
translation-type: tm+mt
source-git-commit: 9140868f7ccf1f7d8ead45fd0c3db6c9b4133538

---


# Adobe Analytics-关键概念

此部分包含 Adobe Analytics 的关键概念，有关该概念的简要描述，以及具有该主题额外详细信息的特定文档链接。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 产品 | 描述 | 文档链接 |
|--- |--- |--- |
| Analysis Workspace | 用于构建可靠的自定义分析项目和实现洞察大众化的浏览器解决方案。比Reports&amp; Analytics提供更多报告灵活性 | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Reports &amp; Analytics（以前称为 SiteCatalyst） | 用于报告和分析的浏览器解决方案。Analytics 包中的初学者工具。 | [https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Excel加载项，可让您根据Adobe Analytics数据构建自定义请求，并使用Microsoft Excel对其进行可视化。 | [https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis（以前称为 Discover） | 用于高级数字分析的基于Java的工具。Slade for the-of-life-of-life in Q2019. | [https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench（以前称为 Insight） | 旨在收集、处理、分析与可视化来自多个渠道间在线和离线客户交互的数据。 | [https://marketing.adobe.com/resources/help/zh_CN/insight/client/](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 用于存储和自定义报表的、未经处理的原始数据，您可通过过滤数据运行它。无点击级别。 | [https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | 可以在整个 Adobe Experience Cloud 范围内将移动设备应用程序的移动营销功能整合在一起，以便您了解和提高应用程序的用户参与度。访问地址如下：https://mobilemarketing.adobe.com/ | [https://docs.adobe.com/content/help/en/mobile-services/using/home.html](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange数据连接器(以前称为Genesis) | 将跟踪数据从第三方应用程序导入Analytics，从而在一个中心位置对性能进行端到端可见性。 | [https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| 动态标签管理 (DTM) | 帮助您管理所有网站上的 Analytics、Target 及其他标签，而无需考虑您有多少个域。 | [https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Adobe的下一代网站标签和移动SDK管理功能。 | [https://docs.adobe.com/content/help/en/launch/using/overview.html](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

单击[此处](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)，以获取有关 Adobe Analytics 术语的扩展术语表。

| 术语 | 描述 | 文档链接 |
|--- |--- |--- |
| Prop(自定义流量) | 用于跟踪逐页站点流量活动的维度。Prop 不会在页面之间持续保留。流量变量的关键应用： <ul><li>简单计数以查找特定值的“最流行”</li><li>了解用户如何通过您的网站进行路径分析 </li></ul><br>流量变量示例：页面名称、站点部分、浏览器</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar(自定义转换) | 保留在您自定义的一段时间内的维度。过期选项包括事件过期、访问过期、或 X 日过期，应由将对该变量执行的分析类型驱使。<br>eVar与prop之间的关键区别：</br><ul><li>Prop通常用于路径分析，因为持久性被删除。</li><li>eVar通常用于转化分析。</li></ul><br>转化变量示例：内部搜索条款、内部促销、外部营销活动(s. campaign)</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| 事件/指标(s. events) | 衡量我们希望访客在我们的网站上采取的关键行动的指标。事件有 3 种类型：计数器、数值和货币。事件在被添加到转化变量报表 (eVar) 时是最有用的。eVar 提供所发生情况的质量信息，事件则提供所发生情况的数量信息。<br>eVar与事件之间的关键区别：</br><ul><li>eVar告诉我们哪些人、哪些人或哪些人受影响</li><li>活动测量发生的转化数</li></ul><br>转化事件的示例：订单数、应用程序启动数、潜在客户数、收入。</br> | [https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| 组件 | 可拖放到项目中的维度、量度、区段和时间粒度(日期范围)。 | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| 维度 | eVar、prop、分类和标准Adobe收集的值集合。 | [https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 量度 | 已实施事件和计算量度的集合。 | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 计算量度 | 能够从通过实施获取的现有指标派生自定义指标。 | [https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| 区段 | 能够生成、管理和共享强大而集中的受众区段，并将其应用于您的 Analytics 报表。区段在各 Analytics 产品间共享，还可在整个 Experience Cloud 中共享。 | [https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 时间(日期范围) | 可过滤日期至任何时间段并创建可在分析中重复使用的自定义日期范围。 | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| 可视化 | 丰富的视觉效果，可帮助您在项目中生动地呈现数据。 | [https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| 管理分析 | 能够限制在项目或虚拟报告套件中访问的组件。 | [VRS CurationProject](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[CurrationCompare](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |



## Key features {#concept_216E78AD39DD453D940AE857F4C7D4DF}

<table id="table_5CD38BD3BE854E69B6925EA3F02AFC92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报表 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 文档链接 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 完整报表列表 </td> 
   <td colname="col2"> Adobe Analytics 中所有可用报表的定义。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_descriptions.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自定义流量 (Prop) </td> 
   <td colname="col2">用于逐页跟踪网站流量活动。Prop 不会在页面之间持续保留。流量变量的关键应用： 
    <ul id="ul_A935EC5271684B9599F683C7B31400ED"> 
     <li id="li_58E0596050A34ACC821916EA61E946EF">捕获可与页面查看次数、访问数、访客数或实例数关联的值。 </li> 
     <li id="li_2B4C557AAD0544BE8204C0D7CE587175">找出特定值中“最受欢迎”的部分。 </li> 
     <li id="li_7FA62BE657F047459DF439BFB9F332F5">了解用户如何寻访您的网站。 </li> 
    </ul> <p>流量变量的示例：页面名称、网站区域、浏览器。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/traffic_var.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自定义转化 (eVar) </td> 
   <td colname="col2">主要用于报告转化事件，并在您自定义的时段内持续保留。过期选项包括事件过期、访问过期、或 X 日过期，应由将对该变量执行的分析类型驱使。 <p>转化变量和流量变量之间的关键区别： </p> 
    <ul id="ul_B0A7482A81B94C5F86C06E5507DB393D"> 
     <li id="li_272E414520AA4603AE5EC397B0F93630"> 自定义流量变量与流量量度相关，但与转化无关。通常用于路径分析。 </li> 
     <li id="li_EBBF9A35C64845FE9683540DFA89E7E9">自定义转化变量可与流量和转化相关，并且通常用于转化分析。 </li> 
    </ul> <p>转化变量的示例：内部搜索词、内部促销活动、外部促销活动 (s.campaign)。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/conversion_var_admin.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功事件 (s.events) </td> 
   <td colname="col2"> <p>测量我们希望访客在我们的网站上采取的关键行动。 </p> <p>事件有 3 种类型：计数器、数值和货币。事件在被添加到转化变量报表 (eVar) 时是最有用的。eVar 提供所发生情况的质量信息，事件则提供所发生情况的数量信息。 </p> <p>转化变量和自定义事件之间的关键区别： </p> 
    <ul id="ul_2B95D7437DE444DD9618DBFE6A8612D1"> 
     <li id="li_5951858853334EFA931A5BC57E5C933F">转化变量可告诉我们，什么人、什么事情或什么内容影响了转化。 </li> 
     <li id="li_339755C842714E0DB8DB4DFAA43AB4F7"> 自定义事件可测量有多少转化发生。 </li> 
    </ul> <p>转化事件的示例：订单数、应用程序启动数、潜在客户数、收入。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/success_event.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/success_event.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 网站量度 </td> 
   <td colname="col2"> 显示有关您的网站的数量信息，例如独特访客数、订单数、收入等。每个量度都可置于其他基于项目的报表中。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_site_metrics.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 网站内容 </td> 
   <td colname="col2"> 显示的信息包括网站上哪些页面和区域最为活跃及哪些服务器使用率最高。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_site_content.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 移动 </td> 
   <td colname="col2"> 显示有关从移动设备或平板电脑访问的网站的信息。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_mobile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 移动设备应用程序 </td> 
   <td colname="col2"> <p>显示与您的移动设备应用程序相关的基本使用信息。只要我们的 SDK 得以实施并且报表处于开启状态，这些报表即可供您使用。 </p> <p>此外，Adobe Mobile Services 还创建了一个单独的移动设备应用程序界面，它提供更加全面的应用程序数据，从而允许您了解和改进应用程序的用户参与。 </p> <p>界面访问地址： </p> <p><a href="https://mobilemarketing.adobe.com" format="https" scope="external"> https://mobilemarketing.adobe.com</a> </p> </td> 
   <td colname="col3"> <p>Adobe Mobile Services： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/mobile/</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 路径报表 </td> 
   <td colname="col2"> 显示有关访问网站页面的先后顺序的信息。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_paths.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 产品 </td> 
   <td colname="col2"> 识别单个产品和产品组（类别）对各项转化量度（如收入或结账）的贡献情况。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_products.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客维系 </td> 
   <td colname="col2"> 显示有关客户忠诚度的信息，例如访客回访您的网站的次数和频率。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_visitor_retention.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客资料 </td> 
   <td colname="col2"> 一种报表，可按不同资料类别（包括国家/地区、州、邮政编码及域）来显示客户的购买模式。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_visitor_profile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 营销渠道 </td> 
   <td colname="col2">一种报表，可帮助您了解哪些外部渠道驱使用户访问您的网站，以及哪些内容可最有效地促使转化。提供首次和最近联系属性视图。 <p>这是 Adobe Analytics 中的首选外部流量源报表（而非促销活动或流量源），因为通过它可以最全面地了解付费和免费渠道。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/mchannel/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/mchannel/index.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自定义报表、报表链接、书签和功能板 </td> 
   <td colname="col2"> 在 Analytics 界面中保存和/或与其他人共享您工作的方法。 </td> 
   <td colname="col3">自定义报表： <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/reports_custom.html</a> </p> <p>报表链接： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/user/t_reports_share_link.html</a> </p> <p>书签 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/user/bookmarks.html</a> </p> <p>功能板 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/user/dashboard.html</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

<!-- 

key_metrics.xml

 -->

| 量度名称 | 定义 | 文档链接 |
|---|---|---|
| 完整量度列表 | Adobe Analytics 中所有量度的定义。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/metrics.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics.html) |
| 独特访客 | 在指定时段内访问网站的非重复访客数量。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/metrics_unique_visitors.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html) |
| 访问 | 表示一系列的页面查看操作。访问在访客首次查看网站上的页面时开始，在处于非活动状态 30 分钟后结束。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/metrics_visit.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html) |
| 页面查看 | 访客查看您网站上的页面时即发生页面查看。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/metrics_page_view.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html) |
| 实例 | 定义变量的次数。每当 Adobe Analytics 发现变量中有值时，实例数就会在相应的报表中递增 1。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/metrics_instance.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html) |
| 计算量度 | 可从现有量度创建的自定义量度。例如，如果有收入和访问量，就可以创建一个自定义量度，来计算每次访问的平均收入或被访问数相除的收入（收入/访问数）。 | [https://marketing.adobe.com/resources/help/zh_CN/analytics/calcmetrics/](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) |

## 导入选项 {#concept_7C6DF03B5F9149E2A77F36C739432059}

<!-- 

import_options.xml

 -->

| 选项 | 描述 | 文档链接 |
|---|---|---|
| 分类导入器 | 通过浏览器或 FTP 上载导入与已捕获维度对应的元数据。相对于规则生成器的手动方法。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/c_working_with_saint.html](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| 规则生成器 | 根据用户定义的规则，自动创建维度的元数据分类。 | [https://marketing.adobe.com/resources/help/zh_CN/reference/classification_rule_builder.html](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| 数据源 | 根据维度或只是按天将离线量度导入 Analytics。 | [https://marketing.adobe.com/resources/help/zh_CN/sc/datasources/datasrc_home.html](https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html) |
| Data Connectors | 请参阅[产品](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B)。 |  |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

<!-- 

export_options.xml

 -->

<table id="table_99867D82082D4756872FC3ABD83A33A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 界面报表下载 </td> 
   <td colname="col2"> 从 Analytics 导出数据的最简单方法 </td> 
   <td colname="col3">https://microsite.omniture.com/t2/help/zh_CN/survey/index.html#Downloading_a_Report_Using_ <p>Basic_Options </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Warehouse </td> 
   <td colname="col2">请参阅<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">产品</a>。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report Builder </td> 
   <td colname="col2">请参阅<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">产品</a>。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics API </td> 
   <td colname="col2"> 创建您自己的自定义 Analytics 数据查询。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/developer/documentation" format="https" scope="external"> https://marketing.adobe.com/developer/documentation</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 点击流数据馈送 </td> 
   <td colname="col2"> 从 Analytics 获取数据的最精细方法。设置来自 Analytics 的馈送点击级别。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/clickstream/datafeeds_reference.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 计划数据 </td> 
   <td colname="col2"> 大部分 Adobe Analytics 导出选项都具有计划将数据与报告提交到电子邮件或 FTP 站点的功能。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

<!-- 

data_collection_and_validation.xml

 -->

<table id="table_53039DCCAC1D47F7A1E3485609D13E4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 方法/资源 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 文档链接 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 开发人员资源 </td> 
   <td colname="col2"> 文档概述了可用于收集所有可用平台（Web、移动设备应用程序、视频、Flash 等）间 Analytics 数据的库 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/developer.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 实施指南 </td> 
   <td colname="col2"> 有关数据收集变量的说明，以及有关在 JavaScript 中实施数据收集代码的详细信息。 </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/implement/index.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> App Measurement (s_code) </td> 
   <td colname="col2"> 全局变量管理 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html#" format="html" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/implement/appmeasure_mjs.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 应用程序 SDK </td> 
   <td colname="col2"> 包含应用程序配置文件预填充版本的自定义包。 </td> 
   <td colname="col3">iOS： <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/mobile/ios/?f=requirements</a> </p> <p>Android： </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/mobile/android/requirements.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Tag Management (DTM) </td> 
   <td colname="col2">请参阅<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">产品</a>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VISTA </td> 
   <td colname="col2"> 用于填充报表变量的服务器端方法。VISTA 使用访客分段规则来创建所有在线数据的实时分段。这些规则使您几乎能够以您选择的任何方式来更改数据或对数据进行分段，而无需在您的网站上实施复杂的逻辑。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/VISTA.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 处理规则 </td> 
   <td colname="col2"> 一种用于简化数据收集的方法，它还可用于管理通过管理员工具部分发送到报表的内容。处理规则提供一个界面，可帮助简化 IT 团队和 Web 开发人员的交互，从而能够设置、修改和复制变量。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/reference/processing_rules.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 调试程序选项 </td> 
   <td colname="col2"> 当前有数种可用的调试程序和包嗅探器可帮助验证您的实施。我们的首选调试程序为 Charles。其他调试程序还包括 Adobe Debugger、HTTPFox、Firebug、Omnibug、Fiddler 和 HTTPWatch。 </td> 
   <td colname="col3">Adobe Debugger： <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_CN/sc/implement/debugger.html</a> </p> <p>Charles： </p> <p><a href="https://www.charlesproxy.com/" format="http" scope="external"> https://www.charlesproxy.com/</a> </p> </td> 
  </tr> 
 </tbody> 
</table>
