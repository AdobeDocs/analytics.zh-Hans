---
description: Android 移动库的发行说明汇总。
seo-description: Android 移动库的发行说明汇总。
seo-title: Android
solution: Analytics,Experience Cloud
subtopic: 发行说明
title: Android
topic: 开发人员和实施
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Android{#android}

Android 移动库的发行说明汇总。

>[!NOTE]
>
>要查找当前库版本，请打开调试日志记录。

可在 [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) 和 [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1) 上下载移动库。

## 版本 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

[!DNL Android] SDK版本4.13.4（2017年2月16日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 应用程序内消息传送 </p> </td> 
   <td colname="2"> <p> 修复了在确定受众时无法使用正确应用程序版本的问题。以前当用户升级了应用程序版本，但又没有启动新的生命周期时，会发生此问题。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>生命周期 </p> </td> 
   <td colname="2"> <p> 修复了无法正确报告应用程序版本升级的问题。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>客户获取 </p> </td> 
   <td colname="2"> <p> 修复了首次启动时无法触发延迟深层链接的错误。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

[!DNL Android] SDK版本4.13.3（2017年1月19日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 应用程序内消息传送 </p> </td> 
   <td colname="2"> <p> 修复了需要按下点进按钮才能显示警报消息的问题。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> 改进了对只读数据库访问权限的处理。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>通用链接 </p> </td> 
   <td colname="2"> <p> 修复了在连续启动时会触发若干（附加到客户获取数据的）延迟深层链接的错误。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

[!DNL Android] SDK版本4.13.2（2016年11月10日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 访客 ID 服务 </p> </td> 
   <td colname="2"> <p>Added timestamp and Experience Cloud Organization ID to <code> adobe_mc</code> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 深层链接 </p> </td> 
   <td colname="2"> <p>如今，在调用 <code>trackAdobeDeepLink</code> 时，可正确处理前缀为“<code>adb</code>”和“<code>ctx</code>”的变量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

[!DNL Android] SDK版本4.13.1（2016年10月20日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>客户获取 </p> </td> 
   <td colname="2"> 现在，SDK 支持由 <code>AdobeDataCallback</code> 调用适当返回的自定义的客户获取数据。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>客户获取 </p> </td> 
   <td colname="2"> SDK 现在可以存储 Google Play 引荐变量和自定义变量，并且可以通过 <code>AdobeDataCallback</code> 调用，适当地返回它们。 </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> 现在可以通过 <span class="keyword">mboxParams</span>，在 <code>Target</code> 请求中传递访客 ID 服务参数。 </td> 
  </tr> 
 </tbody> 
</table>

**错误修复**

* 修复了手机的数据请求有时会出现超时的错误。

## 版本 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

[!DNL Android] SDK版本4.13.0（2016年9月15日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>跟踪深层链接 </p> </td> 
   <td colname="2"> <p>新增功能：增加了允许跟踪第三方延迟深层链接的功能。 </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

[!DNL Android] SDK版本4.12.0（2016年8月18日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
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
 </tbody> 
</table>

## 版本 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

[!DNL Android] SDK版本4.11.0（2016年6月22日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
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
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

[!DNL Android] SDK版本4.10.0（2016年5月20日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Target 方法 </td> 
   <td colname="2"> <p>增加了 <code>loadRequest</code> 方法的新语法和示例。 </p> <p>新增了以下 <span class="keyword">Target</span> 方法： </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

[!DNL Android] SDK版本4.9.0（2016年5月5日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 退出和隐私设置 </td> 
   <td colname="2"> <p>您可以在应用程序中实现深层链接，以吸引用户访问应用程序或 Web 链接目标。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

[!DNL Android] SDK版本4.8.3（2016年2月18日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 退出和隐私设置 </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

[!DNL Android] SDK版本4.8.0（2015年11月2日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> 新的Experience cloud访客ID服务方法 </td> 
   <td colname="2"> <p>添加了以下方法： </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> 新的 ADBMobile JSON Config 变量 </td> 
   <td colname="2"> <p>添加了以下变量： </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> PhoneGap 插件方法</span> </td> 
   <td colname="2"> <p>新增了以下方法 </p> <p><b>配置方法</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Target 方法</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
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
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

[!DNL Android] SDK版本4.6.1（2015年9月24日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android SDK 版本 4.6.1</span> </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

[!DNL Android] SDK版本4.6（2015年9月17日）包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p><span class="keyword">Adobe Mobile Services</span> 和 <span class="keyword">Adobe Mobile</span> SDK 允许您将推送消息发送至 <span class="keyword">Analytics</span> 区段。此 SDK 还允许您轻松报告因打开推送消息而打开了您的应用程序的用户。 </p> </td> 
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
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

[!DNL Android] SDK版本4.5包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android Wearable 扩展</span> </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 版本 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

[!DNL Android] SDK版本4.4包括以下更改：

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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

## 版本 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

发行日期：**2014 年 11 月 24 日**

* 新增功能- Adobe Experience Cloud ID集成
* 为清楚起见，改进了调试日志
* 解决了在检查应用程序内消息时可能发生崩溃的问题

## 版本 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

发行日期：**2014 年 10 月 16 日**

* 新增 - 应用程序内消息功能。
* 新增 - 配置文件的位置现在可以在应用程序启动过程中指定。
* 新增 - 目标点现在可以自动更新，而无需新的配置文件。
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* 解决了可能导致无法在特定情况下跟踪应用程序崩溃的问题。
* 在启用了 debugLogging 的情况下清理日志消息并添加更详细的日志记录。
* 多项性能和稳定性增强。

## 版本 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

发行日期：**2014 年 8 月 4 日**

* 解决了在反向链接超时大于或等于 5 秒并禁用了离线跟踪的情况下可能导致生命周期点击未被发送的问题。

## 版本 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

发行日期：**2014 年 7 月 17 日**

* 对于在数据库损坏或无法创建的情况下可能发生的异常添加了相关保护。
* 对于在配置无法加载时可能发生的问题（通常由空上下文引起）添加了相关保护。
* 对于在更新定时操作的上下文数据时可能发生的异常添加了相关保护。

## 版本 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

发行日期：**2014 年 4 月 23 日**

* 修复了在启用反向链接跟踪并在生命周期之前进行跟踪调用时可能发生的问题。

## 版本 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

发行日期：**2014 年 4 月 17 日**

* 新增——蓝牙信标跟踪。
* 新增功能——启用时间戳的应用程序会将崩溃点击回溯到正确的会话。
* 新增功能——启用时间戳的应用程序，在点击中发送上一个会话，该点击会回溯到正确的会话。 （不再为上一会话）。
* 新增——点击批处理。
* 修复了Google Play Referrer跟踪，可配置超时以允许延迟的Google Referrer数据。
* 解决了在特定情况下可能发生的StrictMode警告。
* 解决了在以特定顺序调用某些方法时很少导致库锁定的问题。

## 版本 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

发行日期：**2014 年 2 月 24 日**

* 解决了在调用停止并稍后调用关闭（在此期间没有其他调用）的情况下可能导致媒体时间播放延长的问题。
* 解决了即使在媒体没有播放任何时间长度的情况下仍会发送媒体关闭点击的问题。

## 版本 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

发行日期：**2014 年 2 月 20 日**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## 版本 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

发行日期：**2014 年 1 月 30 日**

* 解决了在数据库损坏的情况下可能导致多个点击被发送的问题。
* 解决了在设备具有错误时间设置的情况下可能导致较大的平均会话时长的问题。

## 版本 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

发行日期：**2014 年 1 月 30 日**

* 对于导致点击量重复的损坏数据库添加了相关保护。
* 添加了最大会话长度限制，以避免在设备时间不正确时出现极大的会话。

## 版本 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

发行日期：**2013 年 11 月 14 日**

* 解决了 trackLocation 数据在特定区域设置下格式不正确的问题。

## 版本 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

发行日期：**2013 年 9 月 27 日**

[!DNL Android] 适用于Experience cloud解决方案的SDK 4.x现已推出，提供以下新增功能：

* 显著的性能增强。所有处理都是在后台线程中执行的，SDK 具有完全安全的线程。
* 地理位置和目标点
* 存留期值
* 定时事件
* 启用/禁用管理
* Audience Manager 支持
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* 对上下文数据和处理规则进行了标准化

## 版本 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

发行日期：**2013 年 9 月 23 日**

* 修复了 Audience Manager 中存在的一个错误，该错误不允许参数中出现空值或键。

## 版本 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

发行日期：**2013 年 9 月 12 日**

* 修复了 linkTrackEvents 中的媒体事件未被添加到请求的错误。
* 修复了修改的 ContextData 在传递到跟踪调用后出现相关潜在异常的问题。

## 版本 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

发行日期：**2013 年 8 月 16 日**

* SSL 连接现在使用严格的主机验证
* 修复了在网络连接丢失和 offlineTracking 被禁用的情况下，点击量在数秒内不断快速重试的错误。

## 版本 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

发行日期：**2013 年 8 月 6 日**

* 添加了对 Adobe Audience Manager 的支持。
* 现在，在启用了生命周期跟踪的情况下，生命周期数据通过 Target Mbox 请求发送。
* 解决了可能导致 SQLite 强制关闭光标，从而生成不需要的日志条目的问题。

## 版本 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

发行日期：**2013 年 6 月 13 日**

* 更新了离线存储，以便使用 SQLite。
* 修复了离线限制可能会重置为默认值 (1000) 的错误。
* 更新了 startActivity，以便现在可接受活动或应用程序上下文。
* 修复了在将 lifecycleSessionTimeout 设置为 0 时导致整个应用程序内出现多个启动事件的错误。

## 版本 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

发行日期：**2013 年 4 月 18 日**

* 修复了某些 UTF8 字符存在的编码问题。

## 版本 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

发行日期：**2013 年 4 月 18 日**

* 修复了导致上一会话长度有时计算错误的问题。
* 新访客 ID 将不再基于 deviceID 或 subscriberID。
* 修复了在对变量中的特殊字符进行编码时可能发生崩溃的问题。

## 版本 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

发行日期：**2013 年 3 月 21 日**

* 修复了在未首先设置 visitorID 的情况下无法读取它的问题。
* 为清楚起见，更改了某些错误日志消息中的命名约定。
* 更改了多个基类的可访问性以避免混淆。
* 多项性能增强

## 版本 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

发行日期：**2013 年 2 月 21 日**

* 已弃用 `offlineThrottleDelay`，因为优化线程后不再需要此设置。为保持向后兼容性，此设置仍然存在，但不再具有任何效果。
* 已修复离线点击缓存可能存在的同步问题。
* 阐明了设置分级变量超过 #5 时的警告消息。
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] &gt; 4.0.
* 多项性能增强。
* 解决了可能由于 URL 格式错误造成的潜在异常。

## 版本 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

发行日期：**2012 年 11 月**

* 新增的 `lifecycleSessionTimeout` 配置变量能让您指定在将应用程序启动视为新会话之前，应用程序启动必须经过的时间长度（秒）。
* 新增了使用 `lifecycleSessionTimeout` 配置设置来设置超时值，以便计算会话长度的功能。
* 修复了安全问题。

## 版本 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

发行日期：**2012 年 10 月**

* 新增对 [Google Play 促销活动跟踪](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/index.html?f=referrer)的支持。

## 版本 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

发行日期：**2012 年 9 月**

* 解决了某些情况下关闭点击量可能造成媒体监控出现循环条件的问题。

## 版本 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

发行日期：**2012 年 8 月**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## 版本 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

发行日期：**2012 年 7 月**

第一版。

## 旧 Android 版本 (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. 建议用户尽可能升级到 3.x 版。

## 版本 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

发行日期：**2012 年 3 月**

* 修复了在使用 contextData 传递数据时在某些情况下导致异常的问题。

## 版本 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

发行日期：**2012 年 2 月**

修复了导致链接跟踪调用对 pev1 - pev3 值进行两次 URL 编码的问题。

向与简易跟踪调用 (trackLight) 一起使用的变量添加了时间戳。

## 版本 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

发行日期：**2012 年 1 月**

* Added [!DNL Android] 3.x and 4.x compatibility.
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## 版本 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

发行日期：**2011 年 6 月**

* 升级了库，当设备没有插 SIM 卡时，会使用设备 ID 作为 访客 ID 值。默认情况下，当没有插 SIM 卡，访客 ID 不存在时，库会使用订阅者 ID 作为访客 ID。

## 版本 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

发行日期：**2011 年 4 月**

* 支持所有平板电脑，包括 Xoom。
* 运行报表时能够搜索报表包和量度。
* 支持推动服务器端处理规则的 contextData （仅限 v15）。
* 支持简易服务器调用（目前为测试版）。
