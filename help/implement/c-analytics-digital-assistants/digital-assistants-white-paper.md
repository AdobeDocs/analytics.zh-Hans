---
description: 'null'
seo-description: 'null'
seo-title: 为数字助理实施Analytics
title: 为数字助理实施Analytics
uuid: c61e6a1a-ec08-4936-905-3f57223 f57 ff
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 为数字助理实施Analytics

<!-- 

<p>https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper </p> 
<p>https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html </p> 
<p>Ticket: https://jira.corp.adobe.com/browse/AN-157750 </p>

 -->

随着云计算、机器学习和自然语言处理取得的最新进展，数字助理摆脱了“大眼夹”(Clippy) 的黯淡时期，正成为日常生活的一部分。使用者现在开始与设备进行交谈，并期待设备能够像人一样自然地聆听、理解并做出回应，例如“Alexa，打开客厅的灯”或“Okay Google，外面的天气如何？”

随着这些平台变得日益成熟，各种企业品牌可以使用同样逼真且自然的方式来向使用者展现其服务。例如，使用者可以提出以下问题：

* “Alexa，问一下我的车何时需要加油。”
* ”小娜，我的支票帐户还有多少余额？”
* “Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 美元。”

本白皮书概要介绍了如何充分利用 Adobe Analytics Cloud 来测量并优化这些类型的体验。

## 数字体验架构概述 {#concept_26AC08D291724223A943C80B1C6F2333}

![](assets/Digital-Assitants.png)

现如今的数字助理大多采用了类似的高层架构：

1. **设备：**&#x200B;带麦克风允许用户提问的设备（如 Amazon Echo 或手机）。
1. **数字助理：**&#x200B;该设备可以与支持数字助理的服务进行交互。此服务便是许多不可思议的事情孕育而生的地方。此服务可将语音转换为机器可理解的意图，并解析请求详情。理解用户的意图后，数字助理会将意图和请求详情传送至负责处理请求的应用程序。
1. **“应用程序”：**&#x200B;可以是手机应用程序，也可以是语音应用程序。应用程序负责对请求做出响应。应用程序对数字助理做出响应，然后数字助理再对用户做出响应。

## 在何处实施 Analytics {#concept_F53A0566589042658DEA5B86B22C10CB}

实施 Analytics 的一个最佳位置是在应用程序内。应用程序可以从数字助理处接收用户[意图](../../implement/c-analytics-digital-assistants/digital-assistants-white-paper.md#section_BB339BDB5C3D40C6B5C426B0E092B48A)和意图详情，并确定如何响应。

在请求的生命周期中，有两个时间点可以用来调用 Analytics Cloud。

1. 在将请求发送至“应用程序”时。如果您在对请求做出响应前需要了解更多关于用户的信息，您应该利于 Audience Manager 功能来获取用户所属的区段。
1. 在应用程序返回响应后。如果您只想记录客户发生的事情，以便日后进行优化，则可以在应用程序返回响应后向 Adobe Analytics 发送请求。如此一来，您可以了解到请求以及系统响应的全部相关信息。

## 新安装 {#section_FD63267479DB47C2A081244A3E65A0CC}

对于一些数字助理，当有人安装该服务时，您将收到通知。特别是当涉及身份验证时更是如此。在这种情况下，您应该向 Adobe 发送&#x200B;*`Install`*&#x200B;事件，方法是将上下文数据设置为 `a.InstallEvent=1`。请注意，此上下文数据并非在所有平台上都可用，但当此上下文数据可用于查看客户维系情况时，则该数据特别有用。以下代码示例会在&#x200B;*`Install`**`Install Date`**`AppID`*&#x200B;和.

**代码示例**

```
GET 
/b/ss/[rsid]/0?vid=[UserID]&c.a.InstallEvent=1&amp;c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c .OSType=Alexa&pageName=install 
HTTP/1.1 
Host:  
<xref href="https: sc.omtrdc.net="" " format="http"  scope="external">
  sc.omtrdc.net 
 Cache-Control: no-cache 
</xref href="https:>
```

## 多个助理或多个应用程序 {#section_81740741752E4142BE42DA4C9DDEEDF5}

您有可能会为多个平台开发应用程序。最佳实践是在每个请求中各包含一个应用程序 ID。这可以在 `a.AppID` 上下文数据中进行设置。Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2

**代码示例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1 
Host: [prefix].sc.omtrdc.net 
Cache-Control: no-cache
```

```
 GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 用户/访客识别 {#section_7CE70FEB43C44B90954702CA30F87D58}

The Analytics Cloud uses the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) (ECID) service to tie interactions across time to the same person. Most of the digital assistants will return a *`userID`* that you can use to keep the activity for different users separate in the ECID service. 大多数情况下，该 ID 是您应该传递到 ECID 服务的内容。有些平台返回的&#x200B;*`userID`*&#x200B;会超过 Analytics 所允许的 100 个字符的上限。If that is the case, Adobe recommends that you hash the *`userId`* to a fixed-length value using a standard hashing algorithm, such as MD5 or Sha1.

虽然您可以使用 ECID 服务执行此操作，但只有在您尝试跨不同设备（例如从 Web 到数字助理）映射 ECID 时，这样做才有意义。如果您所使用的应用程序是移动设备应用程序（例如深层链接），则应该按原样使用 SDK，并发送相应信息。可以使用 setCustomerID 方法将&#x200B;*`userID`*&#x200B;附加到 ECID 服务，以便实现更好的设备整合。However, if your app is a service, use the *`userID`* provided by the service as the ECID, as well as setting it in the setCustomerID. 如此一来，您便可以查看用户在一段时间内使用该数字助理的情况。

**代码示例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 会话 {#section_BA4F996F976043B8993F2F7D24FE27FB}

由于数字助理采用对话方式，因此它们通常使用会话的概念。例如：

**使用者：**“Ok Google，帮我叫一辆出租车”

**Google：**“没问题，你什么时间要用车？”

**使用者：**“晚上 8:30”

**Google：**“好了，司机会在晚上 8:30 来接你”

这些会话务必要保持就事论事。它们可帮助收集更多细节信息，进而让数字助理变得更加自然。

如果对对话实施 Analytics，则应该在启动新会话时执行以下两个操作：

1. **访问 Audience Manager：**&#x200B;获取用户所属的相应区段，以便能够对响应进行自定义。（例如，该用户当前符合多渠道折扣的条件。）
1. **发送新会话或启动事件：**&#x200B;在将首个响应发送至 Analytics 时，包括启动事件。通常，可以通过设置 `a.LaunchEvent=1` 上下文数据来发送此响应。

**代码示例[!DNL Launch, by Adobe]**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 意图 {#section_BB339BDB5C3D40C6B5C426B0E092B48A}

每个数字助理都使用自己的算法来检测意图，然后将意图传递至“应用程序”，以便应用程序了解要采取什么行动。这些意图是对请求的简洁表达。

例如，如果用户表示“Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 美元”，意图有可能是类似于 *`sendMoney`*。

通过将其中每个请求作为 eVar 发送，您将能够对会话应用程序的每个意图运行路径报表。此外，您还想要确保“应用程序”可以处理没有意图的处理请求。对此，我们建议传递&#x200B;*`No Intent Specified`*，而不是将值留空。

**代码示例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

或

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 参数/槽/实体 {#section_041CD1730F9E4096BE75DFF2CC810852}

除了意图之外，数字助理通常还会使用一系列键值对来提供意图详情。这些键值对被称作槽、实体或参数。例如：

“Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 美元”请求将具有以下参数：

* 对象 = John
* 金额 = 20
* 原因 = 晚餐

通常情况下，应用程序中的这些参数数量有限。要在 Analytics 中跟踪这些参数，可将这些参数发送到上下文数据中，然后将每个参数分别映射到一个 eVar。

**代码示例**

```
GET /b/ss/[rsid]/0?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 会话 {#section_17D69D6B298E46E88E175F62F1ACD831}

虽然并不是所有应用程序都能创造收入，但我们仍有必要思考要取得什么样的成功，并为成功设定一些衡量标准。Adobe Analytics 能够测量收入、广告展示次数和其他形式的成功，以及用户行为。

## 错误状态 {#section_E8EFF8D610B24DC899C34E50B058864D}

有时，数字助理会向应用程序提供它不知道要如何处理的输入内容。例如：

“Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 袋煤”

如果出现这种情况，应用程序会请求数字助理提供澄清说明。此外，如果出现了类似于上述内容的请求，您应该向 Analytics 发送一个事件，指示应用程序处于错误状态，并同时发送一个 eVar，以指明发生的错误类型。

请务必包括输入内容不正确和“应用程序”遇到问题等错误。

**代码示例**

```
GET /b/ss/[rsid]/0/?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent] HTTP/1.1 
Host: sc.omtrdc.net 
Cache-Control: no-cache
```

## 设备功能 {#section_6770D82A3B0E4AD5A2172A7E67B0DF20}

虽然大多数平台并不会展示与客户交谈的实际设备，但它们会将设备的功能展示为可用界面（例如音频、屏幕、视频等等）。这一信息非常有用，因为它指明了与用户进行交互时可使用的内容类型。在测量界面时，最好按字母顺序将它们串联起来。

示例: `:Audio:Camera:Screen:Video:`

请注意末尾和开头的冒号。These help when creating segments (for example, give me all interactions with `:Audio:` capabilities).

Amazon 功能：[https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)

Google 功能：[https://developers.google.com/actions/assistant/surface-capabilities](https://developers.google.com/actions/assistant/surface-capabilities)

## 供数字助理使用的 Analytics 报表 {#concept_265BC8E99C5545D0A9B9412C11EE58CC}

实施数字助理应用程序后，您可以在该程序中使用 Adobe Analytics 的全部功能。以下是可使用 Analytics 执行的一些操作示例。

## 监控意图 {#section_6632D9F2EF9045A7A1A4263D3561C78F}

大多数应用程序都具有多个意图和多种不同的功能。You could easily use [!UICONTROL Analysis Workspace] to keep track of the top intents by instances and by users

<!-- 

<p>--- Image of Intents --- </p>

 -->

这样，您可以了解哪些功能最为常用，进而了解是否要采用新功能。

## 请求存在错误 {#section_CF1A79003E784F88A03F4EEF6CDC7A7C}

您将能够监控错误，以了解用户遇到的问题是否有共同之处。

<!-- 

<p>--- Image of Errors --- </p>

 -->

## 事件之间的流动情况 {#section_08FA8EBD384D41ED8CA52EFE438C8CD2}

查看意图流动情况是其中最强大的一个功能。此功能有两个方面的作用。首先，您可以在会话中查看用户对话意图的流动情况。其次，您可以查看较长时间段内用户意图的流动情况，以了解用户对“应用程序”的使用的变化情况。

## 示例 {#concept_2B13D5E7A8E042D1A4B7BB80BBAACD12}

**预先安装的应用程序**

<table id="table_70BF4E41D0BE4482BD925FB3A1768CE0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 人员 </th> 
   <th colname="col2" class="entry"> 设备响应 </th> 
   <th colname="col3" class="entry"> 操作/意图 </th> 
   <th colname="col4" class="entry"> 获取请求 </th> 
   <th colname="col5" class="entry"> Analytics 数据 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 播放 Spoofify </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Spoofify” </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. a. launchEvent=&amp; c. Encent= Play&amp; pageName=播放App HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_E80B0BBEBE764023BB9B49FE5F15B918"> 
      <li id="li_9BC2CCABB0ED4246A57C37633666CDE2">访客 ID </li> 
      <li id="li_1E7F9E979A3D49CE90899CE82C70BCD0">应用程序版本 </li> 
      <li id="li_C4BD7653B0FA47F6A3E4F1FF18138F10">启动次数 </li> 
      <li id="li_B7FA47CBD75747E8A8A25E228C90E524">意图 </li> 
      <li id="li_48274BA200704730A22C85FD682AE3B0">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更改歌曲 </p> </td> 
   <td colname="col2"> <p> “好的，您想要听哪首歌曲？” </p> </td> 
   <td colname="col3"> <p> 更改歌曲 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Endo= changeong&amp; pageName= AskForsong HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_AE8CF669F06547FDA68801F20BD8CBCE"> 
      <li id="li_5A03E41891AF4F37A3BE05BC11F197BC">访客 ID </li> 
      <li id="li_435FF7DEB169466E8C3F9258C91315D1">应用程序版本 </li> 
      <li id="li_AB2B602D9DC74B3D951A0942B6CF8B39">意图 </li> 
      <li id="li_C9F87F3BB7104C9C978BB046C5DB9092">*空白播放列表 </li> 
      <li id="li_FB762962468A44A18DF93488EC2CB848">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Celine Dion 的“My Heart Will Go On” </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Celine Dion 的‘My Heart Will Go On’” </p> </td> 
   <td colname="col3"> <p> 更改歌曲 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. Encunt= changePlaylist&amp; pageName= ActionPlaySong&amp; c songID=[012345] HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_2AFEE1E928A8499E96B1BC6C5CC21F81"> 
      <li id="li_4BDF8093373A4DA1BB24A608FAC5B7CF">访客 ID </li> 
      <li id="li_79B4FACCD333472EB9FC1F94B904AFB4">应用程序版本 </li> 
      <li id="li_3EDAB6208CB24213A934167BD08BD1AE">意图 </li> 
      <li id="li_C8E6609F9E0A45A8AED15F73374F40B2">歌曲 ID </li> 
      <li id="li_C4D99387C4D748189E15476F5E03BB76">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更改播放列表 </p> </td> 
   <td colname="col2"> <p> “好的，您想要使用哪个播放列表？” </p> </td> 
   <td colname="col3"> <p> 更改播放列表 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Endo= changePlaylist&amp; pageName= AskForPlayList HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_913CF31C3EB34BDB819AD54D28F9DE5D"> 
      <li id="li_93036A142FB34A73A95B8AB114EA99C3">访客 ID </li> 
      <li id="li_F699CDD7866C4EB4BECFF0FAA4689736">应用程序版本 </li> 
      <li id="li_6AB1FF7ED6A247FAA8922390410F2F5F">意图 </li> 
      <li id="li_9DF30E2E1958468783FF753D014F1A5F">*空白播放列表 </li> 
      <li id="li_B1106A51B8CD49DD8B566B946176F854">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Usher </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Usher” </p> </td> 
   <td colname="col3"> <p> 更改播放列表 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. Encunt= changePlaylist&amp; pageName= ActionPlayPlayList&amp; c播放列表= Uri HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_B70E7C9BEFA54C2FA8B7485F9BC7CEE7"> 
      <li id="li_2B0319D20189497D8C9981F871D4FBC4">访客 ID </li> 
      <li id="li_78C28F34FC7C41589EB111ADCC5A0D66">应用程序版本 </li> 
      <li id="li_8ACF819CF80E4E8F942E0903DF75AE33">意图 </li> 
      <li id="li_49F407E43F474356A5F131F82B6C4EB9">播放列表 </li> 
      <li id="li_7380EC51B0DE420EB5DD48BCE21B0567">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 关闭音乐 </p> </td> 
   <td colname="col2"> <p> *无响应，音乐关闭 </p> </td> 
   <td colname="col3"> <p> 关 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Entant= Off&amp; PageName= TurnSoffic HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BCA19F2A98CC42788A23E668B260F553"> 
      <li id="li_12A9DA8684B2479D90F3C357AE4F1D15">访客 ID </li> 
      <li id="li_9E543F7F12D247D0900E5B1BE8EB0F61">应用程序版本 </li> 
      <li id="li_9627816FE3594C418EC52DAD42501BCA">意图 </li> 
      <li id="li_5D59C5D8D0F34F5193F592A867AE5639">响应 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**要求用户安装应用程序**

<table id="table_C178E3A2C87043A0A2B8C365869102A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 人员 </th> 
   <th colname="col2" class="entry"> 设备响应 </th> 
   <th colname="col3" class="entry"> 操作/意图 </th> 
   <th colname="col4" class="entry"> 获取请求 </th> 
   <th colname="col5" class="entry"> Analytics 数据 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 安装 Spoofify </p> </td> 
   <td colname="col2"> <p> *无响应 </p> </td> 
   <td colname="col3"> <p> 安装 </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; amp；amp；c. a. AsynldEvent=1&amp; c. a. InstallDate=2017-04-24&amp; c. a. appID= SpoNofify1.0&amp; c. OstType= Install&amp; pageName= Install&amp; pageName=安装HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_83A7731E5EA84477906AF4BFB3B50F48"> 
      <li id="li_A23A342B0D5745B3854B90ADFDD15EB2">访客 ID </li> 
      <li id="li_E2F89B771B5F445B995E30C7E76BF2D2">页面 </li> 
      <li id="li_03378BC9365F4020B7E28461AFDCB160">意图 </li> 
      <li id="li_6E1ECC9AF55141D1857688DA6A33DEEA">操作系统版本 </li> 
      <li id="li_A4D06A0DFBC247499D9586F6B76571C4">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Spoofify </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Spoofify” </p> </td> 
   <td colname="col3"> <p> Play </p> </td> 
   <td colname="col4"> <p> 
     <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. a. launchEvent=&amp; c. Encent= Play&amp; pageName=播放App HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </p> </td> 
   <td colname="col5"> <p> 
     <ul id="ul_8FCA2B1357A8496DAF563775F019404F"> 
      <li id="li_78E84586A5284164B5B577B68A113394">访客 ID </li> 
      <li id="li_977915DC425A43BDA69D9F76ADFBAB0C">应用程序版本 </li> 
      <li id="li_12725E1D4540485B8A3DB2EC82C6AD4C">启动次数 </li> 
      <li id="li_5B7F4487682241C38071A7037157F473">意图 </li> 
      <li id="li_A6AC81D56BF44E07B2FC0F2740CAB237">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更改歌曲 </p> </td> 
   <td colname="col2"> <p> “好的，您想要听哪首歌曲？” </p> </td> 
   <td colname="col3"> <p>更改歌曲 </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Endo= changeong&amp; pageName= AskForsong HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C0FCB407A1344527A532A1EAEF0387E4"> 
      <li id="li_8905BCF15F0F493D90B5F1135AEC149C">访客 ID </li> 
      <li id="li_2D1FAAF35CE24CE49D1AE3F24E4A5A86">应用程序版本 </li> 
      <li id="li_A7D11680A9554414878E6CBD03B66DC4">意图 </li> 
      <li id="li_64308721D00441FBB7E6EA6EDF93C100">*空白播放列表 </li> 
      <li id="li_A1B2C4E27F9E4B61AAA6373DA8CEB8F2">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Celine Dion 的“My Heart Will Go On” </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Celine Dion 的‘My Heart Will Go On’” </p> </td> 
   <td colname="col3"> <p> 更改歌曲 </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. Encunt= changePlaylist&amp; pageName= ActionPlaySong&amp; c songID=[012345] HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_5D782E44875144BF96877897E1180D18"> 
      <li id="li_CB5009ED407A4D4ABF3AAFE73133CC66">访客 ID </li> 
      <li id="li_D15D65E315964E0CBF75A87CF3FCF9B5">应用程序版本 </li> 
      <li id="li_055D7621BE1D44BA8B8C50E2E45DA6DF">意图 </li> 
      <li id="li_1D52C0AB9C12483E9CD7DC216D809E44">歌曲 ID </li> 
      <li id="li_5CFB748D02E84050AE216FDC55C680E2">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更改播放列表 </p> </td> 
   <td colname="col2"> <p> “好的，您想要使用哪个播放列表？” </p> </td> 
   <td colname="col3"> <p> 更改播放列表 </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Endo= changePlaylist&amp; pageName= AskForPlayList HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_7167AE13BBC64CC99E4A81B1FF6C9208"> 
      <li id="li_15554F7C8AC3487797A2FB65C8C1E636">访客 ID </li> 
      <li id="li_11254FBCFA60436FB705D5FE4C313CC5">应用程序版本 </li> 
      <li id="li_4F3AE5B191DB4E73A2C08065A3D75188">意图 </li> 
      <li id="li_7F03D76A26254E65AAEB8E7D647895CA">*空白播放列表 </li> 
      <li id="li_DFB50E6BCEAF440D942B30A56CDD1503">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 播放 Usher </p> </td> 
   <td colname="col2"> <p> “好的，正在播放 Usher” </p> </td> 
   <td colname="col3"> <p> 更改播放列表 </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= SpoNofify1.0&amp; c. Encunt= changePlaylist&amp; pageName= ActionPlayPlayList&amp; c播放列表= Uri HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_BE5815D13CFA48408B4612D220356518"> 
      <li id="li_716EA824A56241A282FD1774A51CF52C">访客 ID </li> 
      <li id="li_02CC3C2A66E44BB4BA865893F3206A6C">应用程序版本 </li> 
      <li id="li_558B15EC8605495B8DC01E644602FC4F">意图 </li> 
      <li id="li_21599097A3B14E368693C77CC7BA8ADD">播放列表 </li> 
      <li id="li_70F4254A33704DA18D4D22028A1656E4">响应 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 关闭音乐 </p> </td> 
   <td colname="col2"> <p> *无响应，音乐关闭 </p> </td> 
   <td colname="col3"> <p> 关 </p> </td> 
   <td colname="col4"> 
    <code>GET/b/ss/[rsid]/0？vid=[userID]&amp; c. a. appID= Spoifify1.0&amp; c. Entant= Off&amp; PageName= TurnSoffic HTTP/1.1
主持人：sc. omtrdc. net
缓存控制：no-cache </code>
  </td> 
   <td colname="col5"> <p> 
     <ul id="ul_C623E19496DD466DA299AD610CE5ED1D"> 
      <li id="li_6A7AEF89A74C431C84D107E4F23AE223">访客 ID </li> 
      <li id="li_B8CFF6AAB2E2476786026A98337589AF">应用程序版本 </li> 
      <li id="li_534596CB56B24B729AAA801A7B4D9D31">意图 </li> 
      <li id="li_CA3328E5FFF442BAA0F11C51DF2ED53F">响应 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

