---
description: 'null'
seo-description: 'null'
seo-title: 常见问题解答
title: 常见问题解答
uuid: 05724f56-cf98-4ad8 ad0 d-83a5 a4 b1944 a
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# 常见问题解答

## 访问权限/授权 {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q: Do I need to be an <b>Adobe Advertising Cloud or Adobe Advertising Cloud (AMO) customer</b> to access this functionality? </p> </td> 
   <td colname="col2"> <p>答：不需要，非 Advertising Cloud 和非 AMO 的客户都可以使用此功能。 </p> <p>AMO 客户可以利用现有的 Analytics-AMO 集成；他们将无法使用 Ad Analytics。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：哪些 <b>Adobe Analytics SKU</b> 使您可以使用 Advertising Analytics？ </p> </td> 
   <td colname="col2"> <p>答：Advertising Analytics 适用于 Adobe Analytics <a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html" format="html" scope="external">Select</a>、<a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html" format="html" scope="external">Prime</a> 和 <a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html" format="html" scope="external">Ultimate</a> 三种 SKU 版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我们是否必须<b>支付额外费用</b>才能使用 Advertising Analytics？ </p> </td> 
   <td colname="col2"> <p>答：不需要。除了需要进行适当的 SKU 配置之外，Advertising Analytics 不会产生额外成本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：Advertising Analytics 是否会对我的<b>服务器调用使用情况</b>产生不利影响？ </p> </td> 
   <td colname="col2"> <p>答：不会，Advertising Analytics 使用特殊的数据源类型，不会产生服务器调用成本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：如果我<b>已使用 Advertising Cloud/AMO</b>，我是否仍可以使用 Advertising Analytics 功能？ </p> </td> 
   <td colname="col2"> <p>答：任何兼容的搜索引擎帐户都会被传递到 Advertising Analytics 并以只读方式显示。所有的编辑或更新都应在 Advertising Cloud/AMO 中处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我拥有正确的 SKU，但为什么我仍<b>无法访问</b> Advertising Analytics？ </p> </td> 
   <td colname="col2"> <p>答：Advertising Analytics 仅适用于 Adobe Analytics 管理员；但是，管理员可以向非管理员授予访问权限。请联系您的管理员获取访问权限。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用 Advertising Analytics {#section_3A70C6C4D5A842B2981F0257A01F95FF}

<table id="table_4EC69262B7AB4DF49E736CF3B0362302"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>问：Advertising Analytics 中包含哪些<b>搜索引擎帐户</b>？ </p> </td> 
   <td colname="col2"> <p>答：搜索引擎帐户包括 Google AdWords 和 Microsoft Bing。 </p> <p>注意：Microsoft Bing 于 2019 年 3 月 31 日收购了 Yahoo Gemini。因此，现已不再提供 Yahoo Gemini 广告帐户选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我可以在哪里<b>访问</b> Advertising Analytics？ </p> </td> 
   <td colname="col2"> <p>答：登录到 Adobe Analytics 后，导航至<span class="uicontrol">管理员</span>菜单。然后选择新的菜单选项 <span class="uicontrol">Advertising Analytics</span> 来添加您的搜索引擎帐户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：如何<b>收集数据并将其传递到 Analytics 中</b>？ </p> </td> 
   <td colname="col2"> <p>答：Advertising Analytics 利用一系列自定义 API，通过 Adobe Advertising Cloud 将数据从搜索引擎传递到 Analytics 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：通过此集成，我能获得哪些<b>搜索数据</b>？ </p> </td> 
   <td colname="col2"> <p>答：您可以直接从搜索引擎获得 1) 展示次数、2) 点击次数、3) 成本、4) 质量分数、 5) 平均位置以及 6) AMO ID 实例数（点击实例数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我是否可以根据其他 Analytics 数据（量度/维度）<b>划分 Advertising Analytics 数据</b>？ </p> </td> 
   <td colname="col2"> <p>答：不能，原始搜索数据将以独立数据集的形式进入。不过，您可以通过其他 Analytics 数据对实例数版本的点击数据进行划分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我的帐户的各种<b>状态指标</b>（待定、活动、暂停等）的定义是什么？ </p> </td> 
   <td colname="col2"> <p>答：每个状态指标都标识了每个搜索引擎帐户的一个生命周期阶段。 </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>待定</b>表示该帐户已设置，但尚未提取数据。 </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>暂停</b>表示该帐户之前进行过设置，但现在处于非活动状态。 </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>活动</b>表示该帐户已完全设置并正在提取搜索数据。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我正在尝试<b>将我的 Advertising Analytics 帐户映射到特定报表包</b>，但它在“报表包”模式中不可用。为什么？ </p> </td> 
   <td colname="col2"> <p>答：在将报表包分配到 Advertising Analytics 帐户之前，<a href="../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md#concept_BE491B2A2CAE4D818C218033B985A0FB" format="dita" scope="local">需要为 Advertising Analytics 报表</a>配置所需的报表包。 </p> <p>This is done through a separate Admin page that is accessible from: <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> Report Suites </span>  &gt; <span class="uicontrol"> [select Experience Cloud-enabled report suite] </span>  &gt; <span class="uicontrol"> Edit Settings </span>  &gt; <span class="uicontrol"> Advertising Analytics Configuration </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：是否可以将<b>虚拟报表包</b> (VRS) 分配到 Advertising Analytics 帐户？ </p> </td> 
   <td colname="col2"> <p>答：虚拟报表包不收集数据，因此您不能直接将 Advertising Analytics 帐户映射到虚拟报表包。 </p> <p>但是，您可以将 Advertising Analytics 帐户映射到您想要查看其数据的虚拟报表包的父报表包。 </p> <p>除非您根据 AMO ID（或其分类）在区段逻辑中包含“或”条件，否则搜索引擎量度（点击次数/成本/展示次数）可能不会显示在 VRS 中。示例：添加“存在 AMO ID 的所有点击”将包括该区段中的搜索引擎量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：Advertising Analytics 量度是否可以在<b>营销渠道</b>报表中进行报告？ </p> </td> 
   <td colname="col2"> <p>答：不可以，营销渠道报表中不包含这些量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：搜索数据<b>何时</b>会提取到 Analytics 中？ </p> </td> 
   <td colname="col2"> <p>答：您所在 Analytics 数据中心时区的早上 6 点 (06:00) 左右，系统会从搜索引擎中提取搜索数据。这是收集 AMO 数据并将其插入到报表包中的时间。之后，在将数据插入 Analytics 的过程中，时区会转换为报表包时区。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：<b>在捕获点击次数之前</b>可以捕获哪些数据？即使没有点击次数，我们是否也会捕获展示次数、成本、平均位置等数据？ </p> </td> 
   <td colname="col2"> <p>答：AMO ID 将捕获以下搜索引擎量度：展示次数、成本、点击次数、平均位置和平均质量分数。如果没有点击次数，但具有展示次数，则仍会将展示次数/位置/质量分数数据发送到 Analytics。一般情况下，如果没有点击次数，则也不会有成本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：此类数据是在哪个级别捕获的？<b>访客级别还是点击级别？</b> </p> </td> 
   <td colname="col2"> <p>答：搜索引擎量度是在点击级别捕获的，且关联到 AMO ID（及其分类）。此类数据是概要级别的数据，未关联到访问次数/访客数。因此，搜索引擎量度只能在属于点击级别范围且基于 AMO ID（或其分类）的区段中使用。 </p> <p>AMO ID 也可以在登陆页面上通过点击该页面来捕获（这会将此 ID 关联到访问/访客），此 ID 将保留到下游，以便获取其他 Analytics 量度的点数（直到此 ID 过期或被新的 AMO ID 覆盖）。与任何其他 eVar 一样，AMO ID 会完全合并到数据集中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我们是仅捕获 google.com，还是也会捕获<b>国家/地区版本</b>（例如 google.co.uk、google.it、google.fr 或 google.de）？ </p> </td> 
   <td colname="col2"> <p>A：广告平台分类捕获以下值：“Google Adwords”和“Bing Ads”。 </p> <p>通常的最佳做法是将国家/地区代码包含在营销活动名称中。之后，您可以进一步过滤或分段（例如，如果所有营销活动均以 countrycode_ 开头，则创建一个以“UK_”开头的营销活动 (AMO ID) 区段，可提供仅与 UK 有关的数据）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：量度“AMO 成本”是搜索引擎所报告的每个关键字/广告的成本花费。这是指净成本还是总成本？ </p> </td> 
   <td colname="col2"> <p>答：“AMO 成本”只是向搜索引擎支付的成本。它不包含任何代理费用或搜索优化/管理平台费用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：是否有制定其他广告渠道的计划，例如<b>显示</b>或<b>社交</b>？ </p> </td> 
   <td colname="col2"> <p>答：没有，目前我们在路线图上没有制定针对其他渠道的计划。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自动跟踪与手动跟踪 {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>问：设置我的广告帐户时，它显示<b>自动跟踪</b>可能产生意想不到的后果。会产生什么样的后果？ </p> </td> 
   <td colname="col2"> <p>答： 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">自动模式将尝试以正确的格式将 URL 参数附加到跟踪模板/目标 URL 的末尾。<b>但是，您有责任确保添加的网址参数能够正确保持到最终登陆页面。</b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">自动模式可以将关键字插入到登陆 URL 中，而您的 Web 服务器可能不支持包含特殊字符的关键字。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：如果我最初设置了手动或自动跟踪，稍后<b>可以切换</b>到其他跟踪模式吗？会产生哪些影响？ </p> </td> 
   <td colname="col2"> <p>答：是的，您可以切换，但在进行切换之前，您需要删除旧的跟踪逻辑。这可能导致在切换当天出现一段跟踪停机时间（特别是从手动切换到自动时）。因此，除非绝对必要，否则建议不要进行切换。 </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>从手动切换到自动</b>：删除手动添加到跟踪模板的内容，然后将 Advertising Analytics UI 中的切换开关从手动切换到自动并保存设置。请注意，系统可能需要长达几小时时间来填充自动跟踪代码。 </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>从自动切换到手动</b>：在 Advertising Analytics 设置 UI 中将切换开关从手动更新为自动，然后尽快部署手动跟踪代码。在部署手动跟踪代码时，如果您在搜索引擎跟踪模板中看到自动跟踪代码，请将其删除。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

