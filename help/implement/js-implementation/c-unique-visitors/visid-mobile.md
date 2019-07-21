---
description: 大多数移动设备接受浏览器 Cookie。但是，如果设备不接受 Cookie，则可使用其他方法来唯一识别无线设备。
keywords: Analytics 实施
seo-description: 大多数移动设备接受浏览器 Cookie。但是，如果设备不接受 Cookie，则可使用其他方法来唯一识别无线设备。
seo-title: 识别移动设备
solution: Analytics
title: 识别移动设备
topic: 开发人员和实施
uuid: 2287dd1-cead-485b-a4 d8-94dfb7 cd9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 识别移动设备

大多数移动设备接受浏览器 Cookie。但是，如果设备不接受 Cookie，则可使用其他方法来唯一识别无线设备。

Adobe 已确立了一批可唯一识别大多数移动设备的 HTTP [订户 ID 头](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D)。这些头通常包含设备电话号码（或号码的哈希版本），或其他标识符。大部分的当前设备通常具有一个或多个可唯一识别设备的头，而所有的 Adobe 数据收集服务器都会自动使用这些头替代访客 ID。

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). 但是，如果根据 HTTP 头，设备被识别为移动设备，则会传递“5”，而不是“1”，这指示应返回 wbmp 格式的图像，并且应使用我们识别的无线头列表（而不是 Cookie）来识别设备。

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
   <td colname="col2"> <p>设备被识别为无线设备，或者在图像请求中手动发送 <code>/5/</code>： </p> 
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

## 订户 ID 头 {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

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

您可以使用[动态变量](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)来提取头中的特定值。
