---
description: 逐步完成 DFA Data connectors 集成。
seo-description: 逐步完成 DFA Data connectors 集成。
seo-title: 配置 DFA 集成
title: 配置 DFA 集成
uuid: 4c2ac58a-87c6-46f3-9033-9404bb18c39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 配置 DFA 集成{#configure-the-dfa-integration}

逐步完成 DFA Data connectors 集成。

配置页面提供有关集成的概述以及可获取更多信息的有用链接。Adobe 和 DoubleClick 费用均与此集成相关。请联系这两个组织相应的销售代表，并确保您了解费用结构。

1. Log in to the [!DNL Adobe Analytics].
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![步骤结果](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. 下表解释了通过该向导完成集成所需要的信息。

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 向导页码 </th> 
   <th colname="col2" class="entry"> 字段 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 集成名称 </td> 
   <td colname="col3"> Genesis 在报表包的活动集成列表中显示的集成名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 集成电子邮件地址 </td> 
   <td colname="col3"> 接收与此集成相关的所有通知的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 用户名 </td> 
   <td colname="col3"> 随此集成一起使用的 DFA API 用户名。要允许用户进行 API 登录，请检查 DFA 界面中的 API 属性。在启用 API 登录后，将显示一个密码字段为用户提供密码。将此密码连同用户名一起输入到向导中进行验证。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 密码 </td> 
   <td colname="col3"> DFA API 密码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 广告商 ID </td> 
   <td colname="col3"> <p>DFA 广告商 ID 或父 Floodlight 配置 ID。Data connectors 使用此 ID 标识要跟踪的 DFA 广告商（1.5 版本的集成）。此广告商ID未在集成的2.0版本中使用-将查找并使用父Floodlight Configuration ID。请参阅屏幕上的说明 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA 广告变量 </td> 
   <td colname="col3"> 用于接收 DFA 促销活动属性、展示次数和点击量数据的 Analytics eVar。通常，此为跟踪代码 eVar (<span class="varname"> s. campaign </span>)，但您可以选择任何可用的eVar。Data connectors 还将以下 DFA 相关分类添加到选定 eVar： <p><b>促销活动</b>：向包含常见消息的多个网站提供的广告集合。 </p> <p><b>网站名称</b>：提供广告服务的网站。 </p> <p><b>广告名称</b>：在您的 DFA 帐户中定义的广告名称。 </p> <p><b>网站版面名称</b>：提供广告服务的网站和页面。 </p> <p><b>交付工具</b>：DoubleClick for Advertisers。 </p> <p><b>渠道</b>：横幅广告。 </p> <p><b>成本结构</b>：CPM、CPC 或固定成本，具体取决于广告的成本结构。 </p> <p><b>创作名称</b>：与广告/版面/创作 ID 关联的创作名称。 </p> <p><b>DFA &gt; SearchCenter 重复数据删除</b>：指定在发生 DFA 点进和显示到达时，DFA 应将值置入 Searchcenter 变量中。有关详细信息，请参阅 <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">SearchCenter 重复数据删除</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 展示次数 </td> 
   <td colname="col3"> 用于接收 DFA 展示次数量度数据的自定义事件。展示次数指示提供广告服务的次数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 点击量 </td> 
   <td colname="col3"> 选择接收 DFA 点击量量度数据的自定义事件。点击量指示访客点击广告的次数，它由 DFA 的重定向测量。点击量量度与 Analytics 点进次数量度关联。 <p>注意：DFA 点击量和 Analytics 点进次数可能因为数据收集方式的不同而不能完全匹配。For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 显示到达变量 </td> 
   <td colname="col3"> <p>用于接收 DFA 显示到达数据的 Analytics eVar。显示到达变量可帮助您了解显示到达次数如何影响网站上的转化率。 </p> <p>Data connectors 将添加到 DFA 广告变量的相同 DFA 相关分类添加到此 eVar（参见上文）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 自上次查看以来的时间（显示到达时间段变量） </td> 
   <td colname="col3"> 用于接收自上次查看以来的 DFA 时间数据的 Analytics eVar。自上次查看以来的时间指示自上次广告显示到达起过去的时间量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 显示到达次数 </td> 
   <td colname="col3"> 用于接收 DFA 显示到达次数量度数据的自定义事件。结合使用显示到达次数事件和显示到达变量，以了解哪些促销活动虽没有影响直接点进，但可能在后续的某个时候起到将流量引导至网站的作用。 <p>Data connectors 将选定的自定义事件重新命名为“显示到达次数”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA 查询失败 </td> 
   <td colname="col3"> （可选）用于接收任何报告的 DFA 查询失败消息代码的 Analytics eVar。可能的 DFA 消息代码包括： 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>：无 DoubleClick Cookie。 </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>：用户已退出。 </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>：无促销活动历史记录。 </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>：查询错误（超时、服务器故障等）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> 超时事件 </td> 
   <td colname="col3"> <p>该 Analytics 计数器事件在每次<span class="varname"> s. maxDelay </span> 定时器过期，未从DFA服务器收到响应。Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

