---
description: Adobe 使用 Cookie 来跟踪独特的浏览器/设备。
keywords: Analytics Implementation
subtopic: Visitors
title: 识别独特访客
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: ht
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# 识别独特访客

Adobe 使用 Cookie 来跟踪独特的浏览器/设备。

## Analytics 访客 ID 订购 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics 提供了多种识别访客的机制。下表列出了在 Analytics 中识别访客的不同方法（按照优先级排序）：

| 使用顺序 | 查询参数（收集方法） | 显示时间 |
|---|---|---|
| 1 | vid (s.visitorID) | 已设置 s.visitorID |
| 2 | aid (s_vi cookie) | 在您部署访客 ID 服务或配置访客 ID 宽限期之前，访客已拥有一个现有的 s_vi Cookie。 |
| 3 | mid（由 Experience Cloud 访客 ID 服务设置的 AMCV_ Cookie） | 访客的浏览器接受 Cookie（第一方） |
| 4 | fid（回退 Cookie） | 访客的浏览器接受 Cookie（第一方） |
| 5 | IP 地址、用户代理、网关 IP 地址 | 访客的浏览器不接受 Cookie。 |

在许多情况下，您可能会在一次调用中看到 2 或 3 个不同的 ID，但是 Analytics 会将上表中出现的第一个 ID 用作正式的访客 ID。例如，如果您正在设置一个自定义访客 ID （包含在“vid”查询参数中），那么该 ID 将在同一次点击中出现的其他 ID 之前被使用。

> [!NOTE]每个 Analytics 访客 ID 均与 Adobe 服务器上的一个访客资料关联。无论任何访客 ID Cookie 是否过期，访客资料在处于至少 13 个月的非活动状态之后会被删除。

## 自定义访客 ID

您可以实施自定义方法，通过设置 s.visitorID 变量来识别访客。

自定义访客 ID 可以在通过唯一方式识别访客的网站上使用。例如，当用户使用用户名和密码登录网站时，就会生成一个 ID。

如果能够获得和管理用户的[!UICONTROL 访客 ID]，则可以使用以下方法设置 ID：

| 方法 | 描述 |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) 变量 | 如果在浏览器中使用 JavaScript，或者如果使用任何其他 AppMeasurement 库，则可以在数据收集变量中设置访客 ID。 |
| 图像请求中的查询字符串参数 | 此功能允许您通过硬编码图像请求中的 [!UICONTROL vid 查询字符串]参数将[!UICONTROL 访客 ID] 传递到 Adobe。 |
| 数据插入 API | 如果设备使用的无线协议不接受 JavaScript，则可以将包含 `<visitorid/>` XML 元素的 XML post 从您的服务器发送到 Adobe 收集服务器。 |
| URL 重写和 VISTA | 部分部署架构支持使用 URL 重写，以便在无法设置 Cookie 的情况下保持会话状态。在此类情况下，Adobe 工程技术服务可以实施 [!DNL VISTA] 规则来查找页面 URL 中的会话值，然后设置其格式并置入 [!UICONTROL visid] 值。 |
>[!CAUTION]
>**自定义访客 ID 必须足够具体/独特&#x200B;**：如果自定义访客 ID 的实施无效，则可能会导致数据错误和报表性能不佳。如果自定义访客 ID 不够独特或具体，或者未正确设置为通用默认值（例如字符串“NULL”或“0”），则 Adobe Analytics 会将多个不同访客的点击视为单个访客的点击。这种情况会导致数据不正确，访客计数过低，且该访客的区段无法正常工作。如果自定义访客 ID 不够具体，还会导致数据无法在 Analytics 报表集群中的各个节点之间正确分布。在这种情况下，一个节点会变得过载，无法及时处理报表请求。最终，报表包的所有报表都将失败。<br>自定义访客 ID 实施不当可能不会立即影响报表的性能，因为 Analytics 处理不平衡数据通常需要几个月；但是，随着时间的流逝，如果自定义访客 ID 值实施不当，则可能会导致问题，要求 Analytics 禁止处理受影响的报表包。</br><br>实施人员应遵循以下准则：单个自定义访客 ID 值绝不能超过报表包流量的 1%。尽管对于大多数报表包来说，1% 的标准已经足够，但是对于大型报表包而言，可能存在一些实际限制，导致报表性能受到影响，致使其值低于 1%。</br>

## Analytics 访客 ID

当用户访问您的网站时，Adobe Web 服务器会设置一个永久性 Cookie，并将其包含在对浏览器的 HTTP 响应中。此 Cookie 是在指定的数据收集域中设置的。

请求发送至 Adobe 数据收集服务器后，将检查头是否存在访客 ID Cookie (`s_vi`)。如果此 Cookie 位于请求中，则将其用于识别访客。如果不在，服务器会生成一个唯一的访客 ID，并将其设置为 HTTP 响应头中的 Cookie，然后随请求发送回来。该 Cookie 会保存在浏览器中，并在后续访问该站点时发回到数据收集服务器，这也让系统能够在访客每次访问站点时对其进行识别。

### 第三方 Cookie 和 CNAME 记录 {#section_61BA46E131004BB2B75929C1E1C93139}

有些浏览器（如 Apple Safari）不再存储来源域与当前网站所在域不匹配的 HTTP 头中设置的 Cookie（这是第三方上下文中使用的 Cookie 或第三方 Cookie）。例如，如果您在 `mysite.com` 上，您的数据收集服务器为 `mysite.omtrdc.net`，那么从 `mysite.omtrdc.net` 的 HTTP 标头中返回的 Cookie 可能会遭到浏览器的拒绝。

为了避免这种情况，很多客户为其数据收集服务器实施了 CNAME 记录，以此作为[第一方 Cookie 实施](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)的一部分。如果 CNAME 记录被配置为将客户域上的主机名映射至数据收集服务器（例如将 `metrics.mysite.com` 映射至 `mysite.omtrdc.net`），则会存储访客 ID Cookie，因为数据收集域现在与网站的域相匹配。这提高了访客 ID Cookie 被存储的概率，但也会增加一些开销，因为需要为数据收集服务器配置 CNAME 记录并维护 SSL 证书。

### 移动设备上的 Cookie {#section_7D05AE259E024F73A95C48BD1E419851}

使用 Cookie 跟踪移动设备时，您可以使用某些设置修改测量方式。Cookie 的默认有效期为 5 年，但您可以使用 CL 查询参数变量 (`s.cookieLifetime`) 来更改此默认期限。要为 CNAME 实施设置 Cookie 位置，请使用 CDP 查询字符串 `s.cookieDomainPeriods`。如果不指定任何值，则默认值为 2。默认位置为 domain.com。对于不使用 CNAME 的实施，访客 ID Cookie 的位置位于 207.net 域中。

## 标识服务

Identity Service 取代了原有的 Analytics 访客 ID 机制，成为了[!UICONTROL 心率]视频测量、Analytics for Target 以及将来实现 Experience Cloud 核心服务与集成所必需的服务。

有关此服务的产品文档，请参阅 [Identity Service](https://marketing.adobe.com/resources/help/zh_CN/mcvid/)。

## 识别移动设备

大多数移动设备接受浏览器 Cookie。但是，如果设备不接受 Cookie，则可使用其他方法来唯一识别无线设备。

Adobe 已确立了一批可唯一识别大多数移动设备的 HTTP 订户 ID 头。这些头通常包含设备电话号码（或号码的哈希版本），或其他标识符。大部分的当前设备通常具有一个或多个可唯一识别设备的头，而所有的 Adobe 数据收集服务器都会自动使用这些头替代访客 ID。

在典型的图像请求中，路径 (`/b/ss/rsid/1`) 中的“1”会使 Adobe 服务器返回 gif 图像，并尝试设置永久性[!UICONTROL 访客 ID] Cookie（`AMCV_` 或 `s_vi`）。但是，如果根据 HTTP 头，设备被识别为移动设备，则会传递“5”，而不是“1”，这指示应返回 wbmp 格式的图像，并且应使用我们识别的无线头列表（而不是 Cookie）来识别设备。

下表根据路径中的返回图像类型值（“1”或“5”），列出了所用 ID 方法的顺序：

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> ID 方法顺序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>默认值： </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">自定义访客 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">订户 ID 头 </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP 地址-用户代理-网关 IP 地址 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>设备被识别为无线设备，或者在图像请求中手动发送 <code> /5/</code>： </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">自定义访客 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">订户 ID 头 </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP 地址-用户代理-网关 IP 地址 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

您还可以在手动图像请求中传递“1”或“5”，但请注意，这些代码是互相排斥的，因此如果始终传递“5”，则即便支持 Cookie，也不会使用它。您可以结合自己的机制，确定设备是否支持 Cookie，如果支持，则可以在图像中传递“1”而不是“5”。在这种情况下，准确性方面的提升会因为支持 Cookie 的移动设备数量而受到限制。

### 订户 ID 头 {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

通常而言，识别用户时使用订户 ID 方法比 Cookie 更为可靠，因为 Cookie 可能会被删除，也可能发生 Cookie 接受问题和网关 Cookie 管理问题。

您可以加入到移动访客所使用的运营商的白名单中，从而改善识别访客过程中的变化。要获得运营商的访客 ID，请联系该运营商以便将您的域加入其白名单。如果您位于某个运营商的白名单中，则还可以获得在其他情况下可能无法获得的订户 ID 头。

下面的头列表用于识别无线设备。处理头的算法为

1. 提取 HTTP 头键（头的名称，如“X-Up-Calling-Line-ID”）
1. 删掉所有非字母（A-Z 和 a-z）字符
1. 将头键转换为小写
1. 将键的结尾部分与下表中的头相比较以查找匹配项：

| 头 | 类型 | 示例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| forwardedfor | ID 或 IP 地址 | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID 或 IP 地址 | X-Wap-msisdn: 8032618185 |
| clientip | IP 地址 | Client-ip: 10.9.41.2 |
| wapipaddr | IP 地址 | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | IP 地址 | x-huawei-NASIP: 211.139.172.70 |
| userip | IP 地址 | UserIP: 70.214.81.241 |
| ipaddress | IP 地址 | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | IP 地址 | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

例如，“callinglineid”可与“X-Up-Calling-Line-ID”及“nokia-callinglineid”相匹配。头类型即能说明头中会包含哪些内容。以下列出头的优先级顺序（如果存在名为“callinglineid”的头，则会用它来替代“subno”）。

您可以使用[动态变量](../implement/vars/page-vars/dynamic-variables.md)来提取头中的特定值。

## 回退 ID 方法

如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。

### 回退访客识别方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x 和 JavaScript H.25.3（2013 年 1 月发布）包含一个新的回退访客识别方法，专门针对某些访客的浏览器会阻止由 Adobe 数据收集服务器设置的 Cookie（称为 `s_vi`）的情况。之前，如果不能设置 Cookie，会在数据收集期间使用 IP 地址和用户代理字符串的组合来识别访客。

在这次更新后，只要遇到标准 `s_vi` Cookie 不可用的情况，即会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 `s_fid`，具有 2 年期限，可用作今后的回退识别方法。在无法设置主 Cookie（`AMCV_` 或 `s_vi`）的情况下，此项更改应会提高访问和访客计数的准确性。

总访问量包含通过 `s_vi` Cookie 或使用回退方法识别的所有访客。

### IP 地址、用户代理、网关 IP 地址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。如果无法设置 `AMCV_` 或 `s_vi` 和 `s_fid` Cookie，则可使用 IP 地址和用户代理的组合来识别访客。
