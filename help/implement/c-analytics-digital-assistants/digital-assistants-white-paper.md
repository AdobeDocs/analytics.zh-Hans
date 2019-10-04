---
description: 'null'
seo-description: 'null'
seo-title: 为数字助理实施 Analytics
title: 为数字助理实施 Analytics
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: de48a1211edd3a4fd35cc455f2002384deeed5be

---


# 为数字助理实施Analytics

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

随着云计算、机器学习和自然语言处理方面的最新进展，数字助理正成为日常生活的一部分。 消费者开始与他们的设备交谈，希望他们以类似人的方式理解和回应。 随着这些平台变得日益成熟，各种企业品牌可以使用同样逼真且自然的方式来向使用者展现其服务。例如，使用者可以提出以下问题：

* “Alexa，问一下我的车何时需要加油。”
* ”小娜，我的支票帐户还有多少余额？”
* “Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 美元。”

本页概述了如何最好地使用Adobe Analytics衡量和优化这些类型的体验。

## 数字体验架构概述

![](assets/Digital-Assitants.png)

现如今的数字助理大多采用了类似的高层架构：

1. **设备：**&#x200B;带麦克风允许用户提问的设备（如 Amazon Echo 或手机）。
1. **数字助理：**&#x200B;该设备可以与支持数字助理的服务进行交互。此服务可将语音转换为机器可理解的意图，并解析请求详情。理解用户的意图后，数字助理会将意图和请求详情传送至负责处理请求的应用程序。
1. **“应用程序”：**&#x200B;可以是手机应用程序，也可以是语音应用程序。应用程序负责对请求做出响应。应用程序对数字助理做出响应，然后数字助理再对用户做出响应。

## 在何处实施 Analytics

实施 Analytics 的一个最佳位置是在应用程序内。应用程序从数字助手接收意图和详细信息，然后应用程序确定如何响应。

请求期间有两次发送数据至Adobe Analytics会很有帮助。

1. 当请求发送到您的应用程序时。
1. 在应用程序返回响应后。

如果您只想记录客户发生的事情，以便日后进行优化，则可以在应用程序返回响应后向 Adobe Analytics 发送请求。您将获得完整的请求内容以及系统如何响应。

## 新安装

对于某些数字助理，当某人安装该技能时（尤其是涉及身份验证时），您会收到通知。 Adobe建议通过设置上下文数据变量来发送“安装”事件 `a.InstallEvent=1`。 此功能并非在所有数字助理中都可用，但在提供该功能时有助于查看保留情况。 以下代码示例将“安装”事件、“安装日期”和“AppID”值发送到上下文数据变量中。

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net" format="http" scope="external">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## 多个助理或多个应用程序

您的组织可能希望应用程序适用于多个平台。 最佳实践是在每个请求中各包含一个应用程序 ID。This variable can be set in the `a.AppID` context data variable. Follow the format of `[AppName] [BundleVersion]`, for example, BigMac for Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 用户／访客识别

Adobe Analytics使用 [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) ，将不同时间的互动与同一人联系起来。 大多数数字助理 `userID` 会返回一个可用于为不同用户保留活动的工具。 在大多数情况下，此值可以作为唯一标识符传入。 某些平台返回的标识符长于允许的100个字符。 在这些情况下，Adobe建议您使用标准哈希算法（如MD5或Sha1）将唯一标识符散列为固定长度值。

当您跨不同设备（例如，Web到数字助手）映射ECID时，使用ID服务可提供最大价值。 如果您的应用程序是移动应用程序，请按原样使用Experience Platform SDK，然后使用该方法发送用户 `setCustomerID` ID。 但是，如果您的应用程序是服务，请使用由服务提供的用户ID作为ECID，并在中设置它 `setCustomerID`。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 会话

由于数字助理采用对话方式，因此它们通常使用会话的概念。例如：

**使用者：**“Ok Google，帮我叫一辆出租车”

**Google：**“没问题，你什么时间要用车？”

**使用者：**“晚上 8:30”

**Google：**“好了，司机会在晚上 8:30 来接你”

会话对于保持情境非常重要，并有助于收集更多详细信息，使数字助理更自然。 在对话中实施Analytics时，启动新会话时有两件事要做：

1. **访问 Audience Manager：**&#x200B;获取用户所属的相应区段，以便能够对响应进行自定义。（例如，该用户当前符合多渠道折扣的条件。）
2. **发送新会话或启动事件：**&#x200B;在将首个响应发送至 Analytics 时，包括启动事件。通常，可以通过设置 `a.LaunchEvent=1` 上下文数据来发送此响应。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## 意图

每个数字助理都使用自己的算法来检测意图，然后将意图传递至“应用程序”，以便应用程序了解要采取什么行动。这些意图是对请求的简洁表达。

例如，如果用户表示“Siri，从我的银行应用中向 John 支付昨晚的晚餐费 20 美元”，意图有可能是类似于 *sendMoney*.

通过以eVar形式发送每个请求，您可以针对会话应用程序的每个意图运行路径报告。 确保您的应用程序也可以处理请求而无意。 Adobe建议将“未指定用途”传入目的上下文数据变量，而不是传入变量。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

或

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## 参数/槽/实体

除了意图之外，数字助理通常还有一组键／值对，其中提供了意图的详细信息。 这些参数可以称为槽、实体或参数。 例如，“Siri,Send John $20 for dinner for my banking app”(Siri, Send John $20 for night baing app)将包含以下参数：

* 对象 = John
* 金额 = 20
* 原因 = 晚餐

通常，应用程序中的这些值有限。 要在Analytics中跟踪这些值，请将它们发送到上下文数据变量中，然后将每个参数映射到eVar。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 错误状态

有时，数字助理会为您的应用程序提供其不知道如何处理的输入。 例如，“Siri, Send John 20袋煤，昨晚在我的银行应用上用餐”

出现这种情况时，请让您的应用程序要求您说明。 此外，向Adobe发送指示应用程序存在错误状态的数据以及指定发生错误类型的eVar。 请务必包括输入不正确的错误和应用程序出现问题的错误。

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## 设备功能

虽然大多数平台不公开用户所接触的设备，但它们确实公开了设备的功能。 例如，音频、屏幕、视频等。 此信息很有用，因为它定义了与用户交互时可以使用的内容类型。 在测量设备功能时，最好将其连接（按字母顺序）。

示例: `":Audio:Camera:Screen:Video:"`

前导和尾部冒号在创建区段时有帮助。 例如，使用功能显示所有 `:Audio:` 点击。

* [Amazon功能](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) （使用Amazon Alexa）
* [Google使用](https://developers.google.com/actions/assistant/surface-capabilities) Google上的操作功能

## 示例

| 人员 | 设备响应 | 操作/意图 | GET请求 |
| --- | --- | --- | --- | ---|
| 安装 Spoofify | 无响应 | 安装 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 播放 Spoofify | "好，演Spofify" | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 更改歌曲 | "好，你想唱哪首歌？" | 更改歌曲 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 《小鲨》 | "好吧，演"粉红方的小鲨鱼" | 更改歌曲 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 更改播放列表 | “好，您需要什么播放列表？” | 更改播放列表 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 播放我最喜爱的歌曲播放列表 | “好，播放您最喜爱的歌曲播放列表” | 更改播放列表 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| 关闭音乐 | 没有响应，音乐会关闭 | 关 | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
