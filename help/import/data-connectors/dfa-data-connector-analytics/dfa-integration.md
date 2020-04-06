---
description: '配置 DFA 集成的过程涉及以下任务 '
keywords: DFA
title: DFA 集成
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# DFA 集成{#dfa-integration}

配置 DFA 集成的过程涉及以下任务：

## 配置 DFA 集成{#configure-the-dfa-integration}

逐步完成DFA Data Connectors集成。

配置页面提供了集成的概述，以及有帮助的链接，以了解更多信息。 与此集成相关的Adobe和DoubleClick费用。 请联系这两个组织相应的销售代表，并确保您了解费用结构。

1. 登录到 [!DNL Adobe Analytics]。
1. 单击 **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. 找到 **[!UICONTROL DoubleClick DFA]**，然后单击 **[!UICONTROL Add New]**。

   ![步骤结果](assets/wizard-01.png)

   在集成向导的每个页面上，提供所需的信息，然后单击 **[!UICONTROL Next]**。 下表说明了通过向导完成集成所需的信息。

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
   <td colname="col3"> 要与此集成一起使用的DFA API用户名。 要启用用户进行API登录，请检查DFA界面中的API属性。 启用API登录后，将显示一个密码字段，用于为用户提供密码。 此密码与用户名一起输入到向导中以进行身份验证。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 密码 </td> 
   <td colname="col3"> DFA API密码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 广告商ID </td> 
   <td colname="col3"> <p>DFA广告商ID或父Floodlight配置ID。 数据连接器使用此ID来标识要跟踪的DFA广告商（集成版本1.5）。 此广告商 ID 未用于 2.0 版本的集成，而是将查找并使用父 Floodlight 配置 ID。查看屏幕上的说明 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA广告变量 </td> 
   <td colname="col3"> 接收DFA活动属性、印象和点击数据的Analytics eVar。 通常，这是跟踪代码eVar( <span class="varname"> s.活动 </span>)，但您可以选择任何可用的eVar。 数据连接器还将以下与DFA相关的分类添加到选定的eVar: <p><b>活动</b>:一组广告，用于承载通用消息的多个网站。 </p> <p><b>站点名称</b>:投放广告的站点。 </p> <p><b>广告名称</b>:广告名称，在您的DFA帐户中定义。 </p> <p><b>站点位置名称</b>:提供广告的网站和页面。 </p> <p><b>投放工具</b>:面向广告商的DoubleClick。 </p> <p><b>渠道</b>:横幅广告。 </p> <p><b>成本结构</b>:CPM、CPC或固定，基于广告的成本结构。 </p> <p><b>创意名称</b>:与广告／置入／创意ID关联的创意的名称。 </p> <p><b>DFA &gt; SearchCenter外部重复数据删除</b>:指定当DFA点进或视图进度发生时，DFA应将值放在Searchcenter变量中。 </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 展示次数 </td> 
   <td colname="col3"> 接收DFA印象量度数据的自定义事件。 展示次数指示投放广告的次数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 点击 </td> 
   <td colname="col3"> 选择接收DFA点击量度数据的自定义事件。 点击量指示访客点击广告的次数，它由 DFA 的重定向测量。点击量量度与 Analytics 点进次数量度关联。 <p>注意：DFA 点击量和 Analytics 点进次数可能因为数据收集方式的不同而不能完全匹配。</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 视图遍历变量 </td> 
   <td colname="col3"> <p>接收DFA视图通过数据的分析eVar。 视图通过变量可帮助您了解视图通过对网站上的转化率有何影响。 </p> <p>数据连接器将与DFA广告变量相同的DFA相关分类添加到此eVar（请参阅上文）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 自上次视图以来的时间(视图时间段变量) </td> 
   <td colname="col3"> 接收自上次视图数据起的DFA时间的分析eVar。 “自上次视图后的时间”指示自上次广告视图后失效的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 视图率 </td> 
   <td colname="col3"> 接收DFA事件量度数据的自定义视图。 结合使用显示到达次数事件和显示到达变量，以了解哪些促销活动虽没有影响直接点进，但可能在后续的某个时候起到将流量引导至网站的作用。 <p>Data Connectors 将选定的自定义事件重新命名为“显示到达次数”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA查询失败 </td> 
   <td colname="col3"> （可选）接收任何报告的DFA查询失败消息代码的Analytics eVar。 可能的DFA消息代码包括： 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>:无DoubleClick Cookie。 </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>:用户已选择退出。 </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>:没有活动历史。 </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>:查询错误（超时、服务器关闭等） </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> 超时事件 </td> 
   <td colname="col3"> <p>分析计数器事件，每次 <span class="varname"> s.maxDelay计时器过期 </span> ，并且未从DFA服务器收到响应时，都会递增该计数器。 使用此事件配置 <span class="varname">s.maxDelay</span> 变量（请参阅“调整 s.maxDelay”</a>）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 针对 DFA 集成的网站更新{#web-site-updates-for-the-dfa-integration}

在 Genesis 为 DFA 集成配置了 Analytics 报表包之后，您必须执行以下操作以配置您的网站和 DFA 环境来支持集成：

### 验证域中的 Cookie 空间{#verify-cookie-space-on-the-domain}

DFA的Data Connectors集成要求您在页面的域上设置cookie。

虽然很少，但某些域已达到某些Web浏览器的最大Cookie容量。 要避免影响访客在您网站上的浏览体验，请咨询您的网络运营部门、开发团队或工程小组，以确认将其他 Cookie 添加到用于 DFA 集成的页面域将不会影响用户体验。您还将需要为此 Cookie 选择一个名称。

### 更新您的 DFA 查询字符串参数{#update-your-dfa-query-string-parameter}

如果您在DFA集成之前已使用Adobe Analytics跟踪广告活动，则可能所有活动（电子邮件、搜索或横幅）都使用相同的查询字符串参数来标识登陆页上的引用活动ID。

要了解何时从DFA广告活动的DFA数据中请求视图和点进数据，数据连接器需要识别访客何时点击了DFA活动横幅广告。 要做到这一点，您必须在 DFA 广告促销活动的登陆页面 URL 中添加一个差异化的查询字符串参数，这样 Data Connectors 就能够区分 DFA 广告促销活动页面和您的网站上可能存在的其他广告促销活动页面。JavaScript 插件中的 `dfa_overrideParam` 用于 DFA。

>[!CAUTION]
>
>尽管促销活动变量可用于其他促销活动，但请不要将它用于 DFA 促销活动。如果您将活动变量设置为DFA活动登陆页,Adobe将无法将展示和点击与DFA活动点进关联起来。 每次访问，Adobe收集服务器都会检查DFA服务器上的上次点进或视图。 鉴于此，应仅在常见登陆页面上包含 DFA 插件代码，以避免不必要的重定向，这些重定向会减缓页面加载时间，这对于 Internet 连接速度较慢的用户尤其不便。

## 更新网站的数据收集代码{#update-your-web-site-s-data-collection-code}

DFA 的 Genesis 集成可利用 DFA Floodlight 配置 ID (dfa_SPOTID)，以提高 DFA 和 Adobe 数据收集系统之间的报表一致性。

>[!NOTE] 术语 Spotlight 已在最近发布的 Google DFA 中更改为 Floodlight。JavaScript 参数 `dfa_SPOTID` 基于 Spotlight 术语而命名，但它可同时用于两个版本。

要在您的网站上启用DFA集成，您必须通过添加以下内容来更新JavaScript数据收集代码：

* DFA 的集成模块
* 添加到集合代码

### DFA 的集成模块 {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA 集成可利用 Adobe Marketing Cloud 集成模块，以向您的核心 JavaScript 数据收集代码 (`s_code.js`) 添加功能。当您从代码管理器下载 AppMeasurement for Javascript 代码时，集成模块将作为 .zip 文件的一部分提供。仅当您在查找该模块方面需要其他帮助时，才请与 Adobe 顾问联系。

在您网站的 `s_code.js` 文件的 `Modules` 部分中插入集成模块代码。

### 添加到收集代码的内容 {#section-8f98c727f1ba414fb8b4f02d696b8791}

基于您在集成向导中激活 DFA 集成时所做的选择，Data connectors 会为您的 JavaScript 数据收集代码生成自定义的添加内容，并通过电子邮件发送给您。将此代码插入 `s_code.js` 文件的主部分（不在 `doPlugins` 函数或任何其他函数中）。

以下示例代码仅供说明；使用在完成数据连接器集成向导后通过电子邮件发送给您的代码。

集合代码由以下组件组成：

* DFA集成设置
* 集成所需的插件

**DFA集成设置**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA集成设置块设置DFA集成所需的变量。 这些变量中每个变量的值来自以下来源：

**CSID**:客户端ID。 完成集成向导后由DFA生成。 数据连接器使用您的DFA CS ID预填充此变量，并在您完成集成向导后在设置电子邮件中向您发送此值。 如果您的帐户启用了高级广告投放，则不需要此变量。

**SPOTID**:Floodlight配置（以前称为Spotlight ID）。 数据连接器根据您在集成向导中指定的DFA帐户信息，使用您的DFA Floodlight配置ID预填充此变量。

**tEvar**:传输变量。 Data Connectors使用您在集成向导中为视图通过变量指定的分析变量名称预填充此变量。 在未与Adobe工程或工程服务部门进行仔细协调的情况下，请勿更改此值。

**errorEvar**:错误变量。 数据连接器使用您在集成向导中为DFA查询失败变量指定的分析变量名称预填充此变量。

**timeoutEvent**:超时事件。 数据连接器使用您在集成向导中为超时事件变量指定的分析变量名称预填充此变量。

**requestURL**:要查询广告信息的远程DFA主机。 除非Adobe另有说明，否则请勿更改此值。

**maxDelay**:指定JavaScript数据收集代码等待DFA Floodlight服务器响应的时间（以毫秒为单位）。 Adobe 建议对此值进行试验，以找出基于您网站流量的最佳值。例如，增加此值通常会收集更多的DFA数据，但如果访客在延迟期间离开站点，则会增加丢失基本访客数据的风险。 降低此值可降低丢失点击数据的风险，但可以减少随Adobe点击数据发送的DFA数据量。

**visitCookie**:用于将DFA调用限制为每次访问一次的Cookie的名称。

**clickThroughParam**:查询字符串（通常包含在所有广告中），它通知集成模块刚刚单击。 此参数在查询字符串中的存在导致DFA Floodlight服务器发生请求，无论访客在过去30分钟内是否已被查询。

**newRsidsProp**:（可选）映射到未使用的“流量”属性变量。 DFA集成会收集该值并将其存储在访问cookie中，以标识为特定访客收集数据的报表包。 仅Adobe工程服务的自定义实施需要此属性。

**集成所需的插件**

集合代码的添加包含了可改进DFA集成操作的附加插件：

* 将DFA查询限制为每次访问一次
* 提供Cookie名称的灵活性。 尽管大多数组织都使用s_dfa，但您可以对DFA集成使用任何有效的Cookie名称。
* 消除不必要的重定向。 由于视图数据是实时收集的，因此Adobe收集服务器和DFA可能会潜在地交换每个页面视图的数据。 当信息不必要时，插件会阻止这些数据交换。

>[!CAUTION]
>
>由插件用于消除不必要的 DFA 查询的其中一个机制是基于域的访问 Cookie。当访客在一次受 DFA 影响的显示到达或点进后跨了多个域时，跨越多个域的集成报表包会夸大点进和显示到达数据。

## 确认 DFA 集成成功{#confirming-a-successful-dfa-integration}

在进行了所有需要的网站更新之后，您可以使用网络流量查看器（如 Charles*、Chrome 开发人员工具或 Firebug*）来确认 DFA 正在与 Adobe 收集服务器通信。

在部署启用了 DFA 的 `s_code.js` 文件后，请使用网络流量查看器来查看 DFA 和 Adobe 数据收集服务器之间的请求，进而查找以下内容：

* 对 DFA 的 `fls.doubleclick.net/json` 服务的请求。此服务的响应方式取决于您所使用的DFA版本。 与DFA集成版本1.5一起：

   * 到 [!DNL ad.doubleclick.net] 的 HTTP 302 重定向。这将在响应中发送一个 Location: 标记，其中包含有关广告访客的信息。
   * 此位置标记可导致到 [!DNL integrate.112.2o7.net/dfa_echo] 的重定向。此服务将有关广告访客的信息转换为JSON(JavaScript Object Notati on)编码字符串。 返回此数据时将显示200 OK HTTP响应。

* 在DFA集成版本2.0（启用高级广告服务）中：

   * [!DNL fls.doubleclick.net] 将通过一个 200 OK 做出直接响应。

无论哪种情况，成功的请求都将导致向包含参数vX的Adobe数据收集服务器发出请求，其中X是视图到eVar编号。 此参数值采用以下形式：DFA-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX。 此字符串包含有关当前访客上次单击和最后印象的数据。

## 调整 s.maxDelay{#tuning-s-maxdelay}

为成功实现 DFA 实施，需要为您的特定网站优化 s.maxDelay。

通常，提高或降低 *`s.maxDelay`* 的决定涉及在获取更多 DFA 访客数据与影响 Adobe 访客数据收集之间的权衡。提高 *`s.maxDelay`* 可获取更多的 DFA 访客数据，但（设置过高）可能影响 Adobe 访客数据的收集。降低 s.maxDelay 值可确保 Adobe 访客数据的收集，但可能损失 DFA 访客数据。

*`s.maxDelay`*&#x200B;不仅在网络通信中封装时间来联系 DFA，它还表示要触发的浏览器延迟并评估这些通信所基于的 JavaScript。这是因为集成模块在将 HTML 元素插入 DOM 后会启动 *`s.maxDelay`* 计时器，DOM 将从 DFA Floodlight 服务器中提取数据。根据同时加载的其他图像或JavaScript文件、访客计算机的速度和特定浏览器实现，浏览器根据这个新的HTML元素实际启动HTTP请求所花费的时间会有所不同。 此外，当从DFA Floodlight服务器检索JSON数据时，浏览器必须评估JavaScript。 这同样由浏览器完全控制，如果同时运行大量JavaScript代码或许多异步JavaScript请求，则可能会延迟。

With this in mind, *`s.maxDelay`* needs to be set dependent up on the complexity of the landing page plus the amount of network delay with DFA. 在某些站点上，降低复杂性的一种可能方法是在页面加载初期触发Adobe收集代码，这样在请求Floodlight服务器时浏览器中就不会再发生这种情况。

Timeout变量在调整时是绝对必需的 *`s.maxDelay`*，因为每次达到s.maxDelay超时时它都会递增。 在决定提高或降低 *`s.maxDelay`* 时，我们建议遵循以下流程：

1. 在将 *`s.maxDelay`* 设置为特定值的情况下收集多天数据。
1. 在相应时间范围内运行 [!DNL Daily Unique Visitors Report]。
1. 运行 [!DNL Timeout Event Report] 以检查经历的超时次数。请记住，每个访客只收集一次超时。

现在掌握了数据，计算

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

请注意，超时百分比实际上考虑了站点的所有访客。 其中一些访客根本不会绑定到DFA，因此超时具有误导性。 要改进此计算，另一项分析可能只考虑设置了 `clickThroughParam` 的页面独特访客（例如 `?CID=1`）。这将显示更准确的信息。

如果超时百分比很低，请考虑减少 *`s.maxDelay`*。 如果它非常高，请提高 *`s.maxDelay`*。降低 *`s.maxDelay`* 时，您将需要重新运行 [!DNL Timeout Report] 以确保超时次数没有显著增加。提高 *`s.maxDelay`* 时，您将需要运行 [!DNL Page Views Report] 以确保页面查看次数不会因数据丢失而下降。每当 *`s.maxDelay`* 发生更改时，请花几天时间来观察数据，以便确保该数据能代表一种趋势，而不只是简单的逐日浮动现象。

*`s.maxDelay`* 的最佳设置是在页面查看次数没有下降的同时使超时百分比达到最小。

当您转到版本2.0的集成时，超时预期会减少，因为消除了302重定向。 测试版客户端的初始发现显示超时的持续减少，因此收集的DFA数据更多
