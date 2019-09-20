---
description: iOS 的发行说明汇总。
seo-description: iOS 的发行说明汇总。
seo-title: iOS
solution: Analytics,Experience Cloud
subtopic: 发行说明
title: iOS
topic: 开发人员和实施
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# iOS{#ios}

iOS 的发行说明汇总。

>[!NOTE]
>
>要查找当前库版本，请打开调试日志记录。

可在 [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) 和 [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios) 上下载移动库。

[4.x 文档](https://marketing.adobe.com/resources/help/en_US/mobile/ios/)

[3.x 文档](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/)

## 版本 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

[!DNL iOS] SDK版本4.13.4（2017年2月16日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>应用程序内消息传送 </p> </td> 
   <td colname="2"> <p> 修复了在确定受众时无法使用正确应用程序版本的问题。以前当用户升级了应用程序版本，但又没有启动新的生命周期时，会发生此问题。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 客户获取 </p> </td> 
   <td colname="2"> <p> 在对应用程序安装中的 Apple Search Ad 数据进行 API 调用之前，添加了三秒钟的延迟（根据文档的推荐）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

[!DNL iOS] SDK版本4.13.3（2017年1月19日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>应用程序内消息传送 </p> </td> 
   <td colname="2"> <p> 如今，当运行 VoiceOver 时，您可以禁用全屏消息。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> 改进了对只读数据库访问权限的处理。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>常规 </p> </td> 
   <td colname="2"> <p> 修复了在使用“应用程序组”的情况下，从后台调用跟踪方法有时可能会导致崩溃的问题。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

[!DNL iOS] SDK版本4.13.2（2016年11月10日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 访客 ID 服务 </p> </td> 
   <td colname="2"> <p> Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 配置 </p> </td> 
   <td colname="2"> <p> 将忽略通过 <code>setAdvertisingIdentifier:</code> 传递到 SDK 的无效 IDFA (00000000-0000-0000-0000-000000000000)。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 深层链接 </p> </td> 
   <td colname="2"> <p>如今，在调用 <code>trackAdobeDeepLink</code> 时，可正确处理前缀为“<code>adb</code>”和“<code>ctx</code>”的变量。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 客户获取 </p> </td> 
   <td colname="2"> <p>如今，来自 Apple 搜索广告的数据将随您的客户获取数据一起发送。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

[!DNL iOS] SDK版本4.13.1（2016年10月20日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 客户获取 </p> </td> 
   <td colname="2"> <p> 现在，SDK 支持由 <code>AdobeDataCallback</code> 调用适当返回的自定义的客户获取数据。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p>现在，可通过 <span class="keyword">mboxParams</span> 在 <span class="keyword">Target</span> 请求中传递<code>访客 ID 服务</code>参数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**错误修复**

* 修复了在向 [!DNL Adobe Analytics] 发送跟踪点击量的同时，尝试将新 ID 同步到 VisitorID 服务可能会导致崩溃的问题。
* Fixed an issue that was causing build warnings when targeting [!DNL iOS] versions older than 8.

## 版本 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

[!DNL iOS] SDK版本4.13.0（2016年9月15日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>应用程序内消息传送 </p> </td> 
   <td colname="2"> <p>新增功能：增加了一个新的消息类型，该类型可打开深层链接 URI。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

[!DNL iOS] SDK版本4.12.0（2016年8月18日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>访客 ID 服务 </p> </td> 
   <td colname="2"> <p> 为了将访客身份转移到基于 Web 的实施，增加了用于将访客身份附加到给定 URL 中的新方法。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>应用程序内消息传送 </p> </td> 
   <td colname="2"> <p>修复了在自定义全屏消息中将 HTML 标记的“target”属性设置为“_blank”时，所发生的崩溃问题。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

[!DNL iOS] SDK版本4.11.0（2016年6月22日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target 方法 </p> </td> 
   <td colname="2"> <p>现在，您可以使用以下新的 <span class="keyword">Target</span> 方法： </p> <p> 
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

[!DNL iOS] SDK版本4.10.0（2016年5月20日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target 方法 </p> </td> 
   <td colname="2"> <p>现在，您可以使用以下新的 <span class="keyword">Target</span> 方法： </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</code> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><code>targetThirdPartyID</code> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><code> targetSetThirdPartyID:</code> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><code> targetPcID</code> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>TVJS 方法 </p> </td> 
   <td colname="2"> <p>现在，您可以使用以下新的 <span class="keyword">Target</span> TVJS 方法： </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><code>targetThirdPartyID</code> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><code> targetSetThirdPartyID</code> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <code> targetPcID</code> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <code> targetSessionID</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>适用于 TVML/TVJS 的 Adobe Target </p> </td> 
   <td colname="2"> <p>现在，您可以在配置 <code>ADBTarget</code> 元素时，使用以下属性名称： </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><code> id</code> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><code> total</code> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <code> purchasedProductIds</code> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <code> mboxParameters</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

[!DNL iOS] SDK版本4.9.0（2016年5月5日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>深层链接 </p> </td> 
   <td colname="2"> <p>您可以在应用程序中实现深层链接，以吸引用户访问应用程序或 Web 链接目标。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

[!DNL iOS] SDK版本4.8.6（2016年3月9日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>跟踪应用程序的崩溃情况 </p> </td> 
   <td colname="2"> <p>The <span class="keyword"> iOS</span> SDK version 4.8.6 contains critical changes that prevent false crashes from being reported. 我们强烈建议您更新到版本 4.8.6。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

[!DNL iOS] SDK版本4.8.5（2016年2月18日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>退出和隐私设置 </p> </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> SDK 4.8.5, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span>, and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

[!DNL iOS] SDK版本4.8.0（2015年11月2日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新的Experience cloud访客ID服务方法 </td> 
   <td colname="2"> <p>新增了以下方法： </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><code> visitorSyncIdentifiers:authenticationState:</code> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><code> visitorSyncIdentifierWithType:identifier:authenticationState: </code> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><code> visitorGetIDs</code> </li> 
    </ul> <p>已将 <code>visitorSyncIdentifiers:identifiers</code> 方法更改为 <code>visitorSyncIdentifiers:</code> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 TVJS 方法 </td> 
   <td colname="2"> <p>新增了以下方法： </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><code> visitorSyncIdentifiersAuthenticationState</code> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><code> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</code> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><code> visitorGetIDsJs</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 ADBMobile JSON Config 变量 </td> 
   <td colname="2"> <p>添加了以下变量： </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

[!DNL iOS] SDK版本4.7.0（2015年10月15日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> tvOS 支持 </td> 
   <td colname="2"> <p>Apple TV 支持 tvOS。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> App Transport Security 支持 </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> 9, Apple introduced App Transport Security, a set of requirements that conforms to best practices for secure connections. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap 插件方法</span> </p> </td> 
   <td colname="2"> <p>新增了以下方法： </p> <p><b>配置方法</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>跟踪方法</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickThrough </li> 
     </ul> </p> <p>新的 Target 方法： </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
     </ul> </p> <p><b>客户获取方法</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Audience Manager 方法</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>访客 ID 服务方法</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> <p><b>应用扩展功能和 Apple Watch 方法</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

[!DNL iOS] SDK版本4.6（2015年9月17日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> <span class="keyword">Adobe Mobile Services</span> 和 <span class="keyword">Adobe Mobile</span> SDK 允许您将推送消息发送至 <span class="keyword">Analytics</span> 区段。此 SDK 还允许您轻松报告因打开推送消息而打开了您的应用程序的用户。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>客户获取方法 </p> </td> 
   <td colname="2"> <p>允许开发人员像用户单击链接一样，发起应用程序客户获取促销活动。这有助于您自行创建手动客户赢取链接并处理应用商店重定向。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>回传 </p> </td> 
   <td colname="2"> <p>回传允许您将 SDK 收集的数据发送至单独的第三方服务器。利用您用来显示应用程序内消息的相同触发器和特征，可以配置 SDK 以将自定义数据发送至第三方目的地。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>标识符 </p> </td> 
   <td colname="2"> <p>新增了以下标识符： </p> <p> 
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <code> setPushIdentifier</code> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><code> setAdvertisingIdentifier</code> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E"><code>trackPushMessageClickThrough</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>适用于 WatchOS 2 的 WatchKit 支持 </p> </td> 
   <td colname="2"> <p>增加了适用于 WatchOS 2 的 WatchKit 支持。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

[!DNL iOS] SDK版本4.5包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> iOS 扩展</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> iOS</span> SDK version 4.5, a new <span class="keyword"> iOS</span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS</span> extension apps. </p> <p>We strongly recommend that you use the <span class="keyword"> iOS</span> SDK rather than using your own wrapper. </p> <p>Apple 提供了一组允许 Watch 应用程序与包含的应用程序之间进行通信（向包含的应用程序发送请求，然后接收响应）的 API。 </p> <p>尽管您可以将跟踪数据作为词典从 Watch 应用程序发送到包含的应用程序，然后在包含的应用程序上调用任何跟踪方法来发送数据，但是这种解决方案存在局限性。 </p> <p>大多数情况下，当用户使用 Watch 应用程序时，包含的应用程序将在后台运行，只有调用 <code>TrackActionInBackground</code>、<code>TrackLocation</code> 和 <code>TrackBeacon</code> 才是安全的。调用其他跟踪方法会干扰生命周期数据，因此您应该专门使用这三种方法，从 Watch 应用程序中发送数据。 </p> <p>Even if these three tracking methods meet your requirements, we recommend using the <span class="keyword"> iOS</span> SDK because the SDK for watch app includes all <span class="keyword"> Mobile</span> features except in-app messaging. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 具有生命周期量度的自定义数据 </p> </td> 
   <td colname="2"> <p>您现在可以包含具有生命周期量度的自定义上下文数据变量。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon</code> and <code> clearCurrentBeacon</code> calls are now available in <span class="keyword"> PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

发行日期：**2014 年 11 月 24 日**

* 新增功能- Adobe Experience Cloud ID集成
* 为清楚起见，改进了调试日志

## 版本 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

发行日期：**2014 年 10 月 16 日**

* 新增 - 应用程序内消息功能。
* 新增 - 配置文件的位置现在可以在应用程序启动过程中指定。
* 新增 - 目标点现在可以自动更新，而无需新的配置文件。
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* 在启用了 debugLogging 的情况下清理日志消息并添加更详细的日志记录。
* 多项性能和稳定性增强。

## 版本 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

发行日期：**2014 年 9 月 18 日**

* Resolved potential crash that could occur if Audience Manager Submit Signal call or [!DNL Target] Load Request call failed due to an unknown network error.

## 版本 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

发行日期：**2014 年 8 月 5 日**

* 解决了 privacyStatus:optunknown 和 offlineEnabled:false 的特定配置可能发生的死锁问题

发行日期：**2014 年 8 月 4 日**

* 解决了在反向链接超时大于或等于 5 秒并禁用了离线跟踪的情况下可能导致生命周期点击未被发送的问题。

发行日期：**2014 年 4 月 17 日**

* 蓝牙信标跟踪。
* 应用程序获取分析.
* 启用了时间戳的应用程序，崩溃点击量回溯至正确的会话。
* 启用了时间戳的应用程序，上一会话在回溯至正确会话的点击中发送。（不再为上一会话）
* 对点击量进行批处理。

## 版本 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

发行日期：**2014 年 2 月 20 日**

* 解决了在不关闭上一项目的情况下打开序列中的相同媒体项目时导致错误行为的问题。

## 版本 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

发行日期：**2014 年 1 月 30 日**

* 解决了在数据库损坏的情况下可能导致多个点击被发送的问题。
* 解决了在设备具有错误时间设置的情况下可能导致较大的平均会话时长的问题。

## 版本 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

发行日期：**2014 年 1 月 30 日**

* 解决了在设备具有错误时间设置的情况下可能导致较大的平均会话时长的问题。

## 版本 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

发行日期：**2013 年 9 月 27 日**

[!DNL iOS] 适用于Experience cloud解决方案的SDK 4.x现已推出，提供以下新增功能：

* 显著的性能增强。所有处理都是在后台线程中执行的，SDK 具有完全安全的线程。
* 地理位置和目标点
* 存留期值
* 定时事件
* 启用/禁用管理
* Audience Manager 支持
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* 对上下文数据和处理规则进行了标准化

## 版本 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

发行日期：**2013 年 9 月 23 日**

* 添加了对 ARM64 和 X64 模拟器架构的支持 (iPhone 5s)

## 版本 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

发行日期：**2013 年 8 月 16 日**

* 通过删除未使用的代码进行了优化。
* 修复了在线程环境中使用 clearVars 时可能发生崩溃的问题。

## 版本 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

发行日期：**2013 年 8 月 6 日**

* 添加了对 Adobe Audience Manager 的支持。
* Lifecycle data is now sent with [!DNL Target] Mbox requests when lifecycle tracking is enabled.

## 版本 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

发行日期：**2013 年 6 月 20 日**

* Fixed a bug introduced in 3.1.7 that was causing issues with lifecycle on devices below [!DNL iOS] 5.0.

## 版本 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

发行日期：**2013 年 5 月 23 日**

* 添加了相应代码，以阻止通过启动应用程序的位置通知和报刊亭通知发送额外的生命周期点击量。

## 版本 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

发行日期：**2013 年 4 月 18 日**

* 修复了导致上一会话长度有时计算错误的问题。

## 版本 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

发行日期：**2013 年 3 月 21 日**

* `ADMS_Measurement.visitorID` 现在会预填充默认值。

## 版本 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

发行日期：**2013 年 2 月 21 日**

* 已弃用 `offlineThrottleDelay`，因为优化线程后不再需要此设置。为保持向后兼容性，此设置仍然存在，但不再具有任何效果。

## 版本 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

发行日期：**2012 年 11 月**

* 修复了在手动设置产品变量时可能发生的 EXEC_BAD_Access 问题。
* 修复了在 mbox 超时的情况下可能发生的无效选择器崩溃。
* 添加了对媒体测量的广告跟踪支持。

## 版本 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

发行日期：**2012 年 10 月**

* 新增的 `lifecycleSessionTimeout` 配置变量能让您指定在将应用程序启动视为新会话之前，应用程序启动必须经过的时间长度（秒）。
* 已修复媒体模块中引起测量对象上设置的事件覆盖由媒体模块设置的事件的问题。
* Fixed an issue that caused an exception when allocating an mbox through the [!DNL Target] integration.

## 版本 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

发行日期：**2012 年 9 月**

* 新增对 armv7s 架构的支持
* 删除了对 armv6 架构的支持
* Minimum supported [!DNL iOS] SDK is now 4.3

## 版本 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

发行日期：**2012 年 8 月**

* 使用媒体监控委托的客户将不再看到两个关闭的事件
* 解决了某些情况下关闭点击量可能造成媒体监控出现循环条件的问题。

## 版本 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

发行日期：**2012 年 7 月**

第一版。

**增强功能**

* 新增了“自动跟踪”功能
* 在最终生成中，库的大小减少至约 90k
* 新增 "trackEvents" 和 "trackAppState" 方法
* 改善了上下文数据支持和功能（建议针对发送的所有信息使用上下文数据）
* 简化了跟踪功能，以便在 5 分钟内完成基本跟踪实施。

**更改**

* [!DNL AppMeasurement] Class 现在为 ADMS_Measurement
* ADMS_Measurement 现在作为适当的 Singleton
* 更改了 eVar、prop、list、hier、pev 的 getter 和 setter
* 传递到 "track" 调用的所有变量将只对该调用存留。

**修改了以下变量**

| 早期（版本 2.x） | 当前（版本 3.x） |
|---|---|
| account | reportSuiteIDs |
| dc | dataCenter |
| pageName | appState |
| contextData | persistentContextData |
| state | geoState |
| zip | geoZip |
| server | appSection |
| debugTracking | debugLogging |
| trackOffline | offlineTrackingEnabled |
| offlineLimit | offlineHitLimit |
| OfflineThrottleDelay | offlineThrottleDelay |

**改变了以下变量的用途：**

* linkURL（与 trackLinkURL 一起发送：）
* linkName（与 trackLinkURL 一起发送：）
* linkType（与 trackLinkURL 一起发送：）
* lightProfileID（与 trackLight 一起发送：）
* lightStoreForSeconds（与 trackLight 一起发送：）
* lightIncrementBy（与 trackLight 一起发送：）
* trackingServerSecure（当启用 SSL 时使用 trackingServer）

**删除了以下变量：**

* timestamp
* userAgent
* dynamicVariablePrefix
* visitorNamespace
* pageURL
* pageType
* referrer
* linkLeaveQueryString
* usePlugins
* useBestPractices（由 AutoTracking 处理）
* delegate
* retrieveLightData
* deleteLightProfiles
* retrieveLightProfiles

## 早期 iOS 版本 (2.x) {#section_5F76C3DA854D4BAEA636A68B3811142B}

The following release notes apply to the 2.x version of [!DNL AppMeasurement] for [!DNL iOS]. 建议用户尽可能升级到 3.x 版。

## 版本 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

发行日期：**2012 年 4 月**

* 增加了对 视频测量的支持。
* 解决了与 linktrackvars 和上下文数据相关的问题。
* 增强了几个额外性能。

## 版本 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

发行日期：**2012 年 3 月**

* 修复了导致离线跟踪在某些情况下停止发送数据的问题。

## 版本 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

发行日期：**2012 年 2 月**

* 修复了当多个线程尝试同时执行跟踪调用时，在某些情况下会导致 EXC_BAD_ACCESS 异常的问题。
* 向与简易跟踪调用 (trackLight) 一起使用的变量添加了时间戳。

## 版本 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

发行日期：**2012 年 1 月**

* 大幅提升跟踪线程的性能。
* 将脱机点击存储移到了未同步到 iCloud 的位置，以符合 iCloud 最佳实践。
* 已将库更新为 Apple 胖二进制格式，这样您就不再需要为您的生成架构加入特定的库。

## 版本 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

发行日期：**2011 年 11 月**

* Added support for [!DNL iOS] 5.
* [!DNL AppMeasurement] for 经过了更新，不再把已弃用的 UDID 值作为 visitorID 的默认值。[!DNL iOS]如果您在应用程序中设置了一个自定义 visitorID（例如 `s.visitorID = @12345`），则您将不会受到此更改的影响。如果您没有设置自定义 visitorID，则不会使用 UDID 作为 visitorID 的值，而是会在初次启动时生成一个随机的 visitorID，然后将其存储在用户默认密钥中。This key is used by [!DNL AppMeasurement] from that point forward. 该密钥还会在标准应用程序备份过程中保存和还原。

* Updated calls from the [!DNL iOS] Best Practices plug-in that are not associated with a page view to send hits using trackLink. 此更新可帮助防止这些点击量记录默认值为“应用程序名称/版本”名称的页面查看。

## 版本 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

发行日期：**2011 年 10 月**

* 改进了委托处理。This fixes an issue that caused the [!DNL iOS] Best Practices Plug-in to crash when bringing the application out of the background.

## 版本 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

发行日期：**2011 年 9 月**

* 已更新标头，以支持使用 prop 和 eVar 51-75。

## 版本 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

发行日期：**2011 年 8 月**

* 运行报表时能够搜索报表包和量度。
* 支持推动服务器端处理规则的上下文数据（仅限 v15）。
* 支持简易服务器调用（目前为测试版）。

