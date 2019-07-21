---
description: 'null'
seo-description: 'null'
seo-title: 归因 IQ 常见问题解答
title: 归因 IQ 常见问题解答
uuid: 90961172-869d-4ed3-baa5-52374e53 b603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# 归因 IQ 常见问题解答

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>问：我在使用新归因模型时，为何“无”行项获得的点数有时会比我预期的要高？</b> </p> </td> 
   <td colname="col2"> <p>答：这可能是由您选择的报告窗口所导致的（相关说明，请参阅<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">此处</a>）。如果报告窗口的开始日期为每月的第一天，并且您使用的是“访客（报告窗口）”回顾时，最有可能出现此问题。为捕获更多的归因回顾（并减少“无”行项），请尝试增加报告窗口所涵盖的时间范围。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：在使用归因模型时，我有时会看到报告窗口之外的日期显示在报表中。为什么？</b> </p> </td> 
   <td colname="col2"> <p>答：这些额外日期是<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">此处</a>所描述的访客报表回顾窗口的人为生成数据。<a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">显示在报告窗口之外的数据</a>一文解释了出现这个问题的原因。Adobe Analytics 将在即将发布的版本中过滤掉这些额外的行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：我可以在归因模型中使用自定义回顾窗口吗？</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：我应该何时使用“访问”归因回顾，何时使用“访客”归因回顾？</b> </p> </td> 
   <td colname="col2"> <p>答：归因回顾的选择实际上取决于您的用例。如果转化通常具有较长的考虑周期（比单次访问所需的时间更长），我们建议您使用访客回顾，或者创建一个具有较长访问时间的 VRS，该 VRS 可更准确地反映考虑周期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：归因模型是否可用在数据馈送或 Data Warehouse 中？</b> </p> </td> 
   <td colname="col2"> <p>答：不可以。由于归因模型是使用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">报表时间处理</a>在报表时间计算的，因此无法将其反映在数据馈送或 Data Warehouse 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：是否只有在使用启用了报表时间处理的虚拟报表包时，我才可以使用归因模型？</b> </p> </td> 
   <td colname="col2"> <p>答：不是，虽然归因模型在后端使用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">报表时间处理</a>，但为方便起见，我们已将其提供给 VRS 和基本报表包。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：Analysis Workspace 中的归因 IQ 是否支持数据驱动或算法归因模型？</b> </p> </td> 
   <td colname="col2"> <p>答：Analysis Workspace 中尚未提供此功能，但我们正在积极解决这个问题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：是否有一些维度或量度不受归因 IQ 支持？</b> </p> </td> 
   <td colname="col2"> <p>A：所有维度都支持归因IQ。</p> 
    <p><u>不</u>受支持的量度（主要是因为它们没有意义）包括： </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> 独特访客 </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">访问次数 </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">发生次数 </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> 页面查看次数 </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">A4T 量度 </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">逗留时间量度 </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">跳出次数 </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">跳出率 </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">登录 </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">退出 </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">页面未找到 </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">搜索 </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">单页面访问量 </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">单次存取 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：归因 IQ 与 Data Workbench 中的归因有何不同？</b> </p> </td> 
   <td colname="col2"> <p>答：Data Workbench 会逐步提供： </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">在更多访客级别的数据源中进行归因的功能，例如广告展示次数和销售点。 </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">算法（<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">最适合的</a>）建模。归因 IQ 仅包括基于规则的模型。 </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">其他可视化图表，例如<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">延时表</a>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：归因 IQ 是否适用于数据源？</b> </p> </td> 
   <td colname="col2"> <p>答：目前，归因 IQ 适用于除概要级别数据源以外的其他所有数据源。 </p> <p> 由于概要级别的数据源未与任何 Analytics 访客标识符绑定，因此无法进行高级归因。交易 ID 数据源也受支持，除非是在已启用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">报表时间处理</a>的虚拟报表中使用此类数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：归因 IQ 是否适用于 <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a> 集成？</b> </p> </td> 
   <td colname="col2"> <p>答：集成量度（包括展示次数、成本、点击次数、平均位置及平均质量分数）属于概要级别的数据源，因此与归因 IQ 不兼容。但是，同标准 Analytics 事件或量度一起使用时，元数据维度（例如匹配类型和关键词）将能够适用于归因 IQ。 </p> </td> 
  </tr> 
 </tbody> 
</table>

