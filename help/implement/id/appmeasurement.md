---
title: 使用AppMeasurement进行访客识别
description: 在使用AppMeasurement实施Adobe Analytics时正确识别访客。
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# 使用AppMeasurement进行访客识别

AppMeasurement是Adobe Analytics用于数据收集的旧版JavaScript库。 虽然AppMeasurement本身提供了用于识别访客的本机方法，但许多现代浏览器会拒绝它尝试设置的Cookie。 Adobe强烈建议在所有实施中使用Adobe Experience Cloud访客ID服务以符合现代浏览器隐私标准。 所有版本的AppMeasurement都与`VisitorAPI.js`捆绑在一起，JavaScript库用于实施访客ID服务。

## 使用访客ID服务识别访客（推荐）

使用此部分可创建Adobe Analytics与访客ID服务之间的基本集成。 确保您已做好以下准备：

* 下载[最新版本的AppMeasurement](https://github.com/adobe/appmeasurement)。 下载的库包含`AppMeasurement.js`和`VisitorAPI.js`。
* 开发[报表包ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)。
* [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)的所需域。
* 您的IMS组织ID：
   1. 使用您的Adobe ID凭据登录[experience.adobe.com](https://experience.adobe.com)。
   1. 在Experience Cloud界面中的任意位置，按`[Cmd]` + `[I]` (iOS)或`[Ctrl]` + `[I]` (Windows)。
   1. 出现&#x200B;**[!UICONTROL 用户数据调试器]**。 选择&#x200B;**[!UICONTROL 分配的组织]**&#x200B;选项卡。
   1. 展开所需的IMS组织。
   1. 找到&#x200B;**[!UICONTROL ID]**&#x200B;字段。

拥有上述资源后，请参阅以下基本示例页面，其中包含将数据发送到Adobe Analytics所需的最低调用数：

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>您可以通过将`Visitor`的存在分配给自定义变量来跟踪点击是否使用访客ID服务：
>
>```js
>s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI Present" : "VisitorAPI Missing";
>```

## 使用`s_vi` Cookie识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

如果贵组织未使用访客ID服务，则AppMeasurement将使用其自身的访客识别形式。 当访客首次访问您的网站时，库会检查[`s_vi`](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 此Cookie在匹配[`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)（对于HTTPS）或[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)（对于HTTP）的域中设置。

* 如果您参与[托管证书计划](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/adobe-managed-cert)，您的跟踪服务器通常是第一方域，使`s_vi` Cookie成为第一方。
* 如果您未参与托管证书计划，则跟踪服务器通常是`adobedc.net`、`omtrdc.net`或`2o7.net`的子域，从而使`s_vi` Cookie成为第三方Cookie。 由于现代浏览器隐私惯例，第三方Cookie被大多数浏览器拒绝。 被拒绝后，AppMeasurement会尝试改为设置第一方回退Cookie (`fid`)。

如果您正确设置`trackingServerSecure`，则无需进一步的访客识别措施。

## 使用`visitorID`识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)变量可让您的组织完成识别访客的独立控制。 如果您使用`visitorID`，请注意以下限制：

* 每次点击必须包含相同的`visitorID`值才能计为单个访客。
   * 任何忽略`visitorID`的点击都会自动尝试使用其他访客识别方法，将它们视为单独的访客。
   * 任何包含与上一次点击不同的`visitorID`值的点击都将被视为单独的访客。
   * Adobe不提供将使用不同访客ID的点击拼合在一起的任何方式。
* 使用`visitorID`标识的访客不支持共享受众、Analytics for Target和客户属性。

有关使用此变量的实施说明，请参阅[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
