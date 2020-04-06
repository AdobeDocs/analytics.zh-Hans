---
description: Adobe 使用 Cookie 来跟踪独特的浏览器/设备。
keywords: Analytics Implementation
subtopic: Visitors
title: 识别独特访客
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 识别独特访客

Adobe 使用 Cookie 来跟踪独特的浏览器/设备。

## Analytics 访客 ID 订购 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics提供了多种识别访客的机制。 下表列表了在Analytics中识别访客的不同方式（按首选项顺序）:

| 使用的订单 | 查询参数（收集方法） | 在 |
|---|---|---|
| 1 | vid (s.visitorID) | 已设置 s.visitorID |
| 2 | aid (s_vi cookie) | 在您部署访客 ID 服务或配置访客 ID 宽限期之前，访客已拥有一个现有的 s_vi Cookie。 |
| 3 | mid（由 Experience Cloud 访客 ID 服务设置的 AMCV_ Cookie） | 访客的浏览器接受 Cookie（第一方） |
| 4 | fid（回退 Cookie） | 访客的浏览器接受 Cookie（第一方） |
| 5 | IP 地址、用户代理、网关 IP 地址 | 访客的浏览器不接受 Cookie。 |

在许多情况下，您可能会在呼叫中看到2个或3个不同的ID，但Analytics将使用上表中显示的第一个ID作为正式访客ID。 例如，如果您正在设置一个自定义访客 ID （包含在“vid”查询参数中），那么该 ID 将在同一次点击中出现的其他 ID 之前被使用。

>[!NOTE]每个 Analytics 访客 ID 均与 Adobe 服务器上的一个访客资料关联。无论任何访客 ID Cookie 是否过期，访客资料在处于至少 13 个月的非活动状态之后会被删除。

## 自定义访客 ID

您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。

自定义访客ID可用于您有唯一方法识别访客的站点。 例如，当用户使用用户名和密码登录到网站时生成的ID。

如果您能够派生和管理用 [!UICONTROL visitor IDs] 户，则可以使用以下方法设置ID:

| 方法 | 描述 |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) 变量 | 如果在浏览器上使用JavaScript，或者如果您使用任何其他AppMeasurement库，则可以在数据收集变量中设置访客ID。 |
| 查询图像请求上的字符串参数 | 这允许您通过硬编 [!UICONTROL visitor ID] 码图像请 [!UICONTROL vid query string] 求中的参数将图像传递给Adobe。 |
| 数据插入 API | 如果设备使用的无线协议不接受 JavaScript，则可以将包含 `<visitorid/>` XML 元素的 XML post 从您的服务器发送到 Adobe 收集服务器。 |
| URL重写和VISTA | 某些部署架构支持在无法设置Cookie时使用URL重写来维护会话状态。 在此类情况下，Adobe 工程技术服务可以实施 [!DNL VISTA] 规则来查找页面 URL 中的会话值，然后设置其格式并置入 [!UICONTROL visid] 值。 |
>[!CAUTION]
>**自定义访客 ID 必须足够具体/独特&#x200B;**：如果自定义访客 ID 的实施无效，则可能会导致数据错误和报表性能不佳。如果自定义访客 ID 不够独特或具体，或者未正确设置为通用默认值（例如字符串“NULL”或“0”），则 Adobe Analytics 会将多个不同访客的点击视为单个访客的点击。这种情况会导致数据不正确，访客计数过低，且该访客的区段无法正常工作。如果自定义访客 ID 不够具体，还会导致数据无法在 Analytics 报表集群中的各个节点之间正确分布。在这种情况下，一个节点会变得过载，无法及时处理报表请求。最终，报表包的所有报表都将失败。<br>自定义访客 ID 实施不当可能不会立即影响报表的性能，因为 Analytics 处理不平衡数据通常需要几个月；但是，随着时间的流逝，如果自定义访客 ID 值实施不当，则可能会导致问题，要求 Analytics 禁止处理受影响的报表包。</br><br>实施人员应遵循以下准则：单个自定义访客 ID 值绝不能超过报表包流量的 1%。尽管对于大多数报表包来说，1% 的标准已经足够，但是对于大型报表包而言，可能存在一些实际限制，导致报表性能受到影响，致使其值低于 1%。</br>

## Analytics 访客 ID

当用户访问您的站点时，Adobe Web服务器会通过将永久Cookie包含在浏览器的HTTP响应中来设置它。 此Cookie在指定的数据收集域上设置。

请求发送至 Adobe 数据收集服务器后，将检查头是否存在访客 ID Cookie (`s_vi`)。如果此 Cookie 位于请求中，则将其用于识别访客。如果Cookie不在请求中，则服务器将生成唯一的访客ID，在HTTP响应头中将其设置为Cookie，并随请求发送回该Cookie。 Cookie存储在浏览器中，并在随后访问网站期间发送回数据收集服务器，这使得在访问期间识别访客。

### 第三方Cookie和CNAME记录 {#section_61BA46E131004BB2B75929C1E1C93139}

有些浏览器（如 Apple Safari）不再存储来源域与当前网站所在域不匹配的 HTTP 头中设置的 Cookie（这是第三方上下文中使用的 Cookie 或第三方 Cookie）。例如，如果您在 `mysite.com` 上，您的数据收集服务器为 `mysite.omtrdc.net`，那么从 `mysite.omtrdc.net` 的 HTTP 标头中返回的 Cookie 可能会遭到浏览器的拒绝。

为了避免这种情况，很多客户为其数据收集服务器实施了 CNAME 记录，以此作为[第一方 Cookie 实施](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)的一部分。如果 CNAME 记录被配置为将客户域上的主机名映射至数据收集服务器（例如将 `metrics.mysite.com` 映射至 `mysite.omtrdc.net`），则会存储访客 ID Cookie，因为数据收集域现在与网站的域相匹配。这增加了访客ID Cookie被存储的可能性，但会引入一些开销，因为您需要配置CNAME记录并维护数据收集服务器的SSL证书。

### 移动设备上的Cookie {#section_7D05AE259E024F73A95C48BD1E419851}

使用 Cookie 跟踪移动设备时，您可以使用某些设置修改测量方式。Cookie 的默认有效期为 5 年，但您可以使用 CL 查询参数变量 (`s.cookieLifetime`) 来更改此默认期限。要为 CNAME 实施设置 Cookie 位置，请使用 CDP 查询字符串 `s.cookieDomainPeriods`。如果未指定值，则默认值为2。 默认位置为domain.com。 对于不使用CNAME的实施，访客ID cookie位置位于207.net域。

## 标识服务

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

有关此服务的产品文档，请参阅 [Identity Service](https://marketing.adobe.com/resources/help/zh_CN/mcvid/)。

## 识别移动设备

大多数移动设备接受浏览器cookie。 但是，当设备不接受cookie时，会使用其他方法来唯一标识无线设备。

Adobe 已确立了一批可唯一识别大多数移动设备的 HTTP 订户 ID 头。这些标题通常包括设备电话号码（或该号码的哈希版本）或其他标识符。 大多数当前设备有一个或多个可唯一标识设备的标题，而所有Adobe数据收集服务器都会自动使用这些标题来代替访客ID。

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). 但是，如果设备被识别为基于HTTP头的移动设备，则传递“5”代替“1”，这表示应返回wbmp格式图像，并且应使用我们识别的无线头的列表（而非cookie）来识别设备。

下表根据路径中的返回图像类型值（“1”或“5”）列表出所使用的ID方法的顺序：

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> ID方法顺序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>默认: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">自定义访客 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">订阅者ID标题 </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP地址-UserAgent-Gateway IP地址 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>设备被识别为无线设备，或者在图像请求中手动发送 <code> /5/</code>： </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">自定义访客 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">订阅者ID标题 </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP地址——用户代理——网关IP地址 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

您还可以在手动图像请求中传递“1”或“5”，但请注意，这些代码是互斥的，因此始终传递“5”在支持时不会利用cookie。 您可以合并自己的机制来确定设备是否支持cookie，如果支持，则在图像中传递“1”而不是“5”。 这种情况下的准确性改进仅限于支持cookie的移动设备的数量。

### 订阅者ID标题 {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

由于Cookie删除、Cookie接受问题和网关Cookie管理问题，用户ID方法通常比用户标识Cookie更可靠。

您可以通过将访客添加到移动访客所使用的运营商的白色列表中来改进标识的更改。 要访问运营商的访客ID，请与运营商联系，将您的域添加到其白色列表。 如果您位于运营商的白色列表中，您还有权访问订阅者ID头，否则您可能无法访问该头。

以下列表的头用于标识无线设备。 处理标题的算法是

1. 提取HTTP头键（头的名称，如“X-Up-Calling-Line-ID”）
1. 裁切掉所有非alpha（A-Z和a-z）字符
1. 将标题键转换为小写
1. 将键的结尾与下表中的结尾进行比较，以找到匹配项：

| Header | 类型 | 示例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID:8613802423312 |
| subno | ID | x-up-subno:swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID:eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid:a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid:595961714786 |
| deviceid | ID | rim-device-id:200522ae |
| forwardedfor | ID或IP地址 | X-Forwarded-For:127.0.0.1 |
| msisdn | ID或IP地址 | X-Wap-msisdn:8032618185 |
| clientip | IP 地址 | 客户端IP:10.9.41.2 |
| wapipaddr | IP 地址 | X-WAPIPADDR:10.48.213.162 |
| 华韦纳辛 | IP 地址 | x-wawei-NASIP:211.139.172.70 |
| userip | IP 地址 | 用户IP:70.214.81.241 |
| ipaddress | IP 地址 | X-Nokia-ipaddress:212.97.227.125 |
| 订阅者信息 | IP 地址 | X-SUBSCRIBER-INFO:IP=10.103.132.128 |

例如，“callinglineid”将匹配“X-Up-Calling-Line-ID”和“nokia-callinglineid”。 标题类型告诉我们标题中的预期内容。 此处列出标题优先级的顺序（如果存在“callinglineid”标题，则使用它而不是“subno”）。

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## 回退 ID 方法

如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。

### 回退访客识别方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x 和 JavaScript H.25.3（2013 年 1 月发布）包含一个新的回退访客识别方法，专门针对某些访客的浏览器会阻止由 Adobe 数据收集服务器设置的 Cookie（称为 `s_vi`）的情况。之前，如果不能设置 Cookie，会在数据收集期间使用 IP 地址和用户代理字符串的组合来识别访客。

在这次更新后，只要遇到标准 `s_vi` Cookie 不可用的情况，即会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 `s_fid`，具有 2 年期限，可用作今后的回退识别方法。在无法设置主 Cookie（`AMCV_` 或 `s_vi`）的情况下，此项更改应会提高访问和访客计数的准确性。

总访问量包含通过 `s_vi` Cookie 或使用回退方法识别的所有访客。

### IP 地址、用户代理、网关 IP 地址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。如果无法设置 `AMCV_` 或 `s_vi` 和 `s_fid` Cookie，则可使用 IP 地址和用户代理的组合来识别访客。
