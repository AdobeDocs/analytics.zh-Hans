---
title: 使用AppMeasurement进行访客识别
description: 在使用AppMeasurement实施Adobe Analytics时正确识别访客。
exl-id: 38797ca5-dc53-431e-95df-3c9e68aead94
TQID: https://experienceleague.adobe.com/vWLzF0HXreytCKr01H4-gKzNlO36ySHA2vbcHvT3cIw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 0%

---

# 使用AppMeasurement进行访客识别

AppMeasurement是Adobe Analytics用于数据收集的旧版JavaScript库。 虽然AppMeasurement本身提供了用于识别访客的本机方法，但许多现代浏览器会拒绝它尝试设置的第三方Cookie。 Adobe强烈建议在所有实施中使用Adobe Experience Cloud访客ID服务以符合现代浏览器隐私标准。 所有版本的AppMeasurement都与`VisitorAPI.js`捆绑在一起，JavaScript库用于实施访客ID服务。

## 使用访客ID服务识别访客（推荐）

确保您已做好以下准备：

* 下载[最新版本的AppMeasurement](https://github.com/adobe/appmeasurement)。 下载的库包含`AppMeasurement.js`和`VisitorAPI.js`。
* 开发[报表包ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)。
* [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)的所需边缘域。
* 您的IMS组织ID：
   1. 使用您的Adobe ID凭据登录[Adobe CX Enterprise](https://experience.adobe.com)。
   1. 在CX Enterprise界面的任何位置，按`[Cmd]` + `[I]` (iOS)或`[Ctrl]` + `[I]` (Windows)。
   1. 出现&#x200B;**[!UICONTROL 用户数据调试器]**。 选择&#x200B;**[!UICONTROL 分配的组织]**&#x200B;选项卡。
   1. 展开所需的IMS组织。
   1. 找到&#x200B;**[!UICONTROL ID]**&#x200B;字段。

获得上述资源后，以下基本示例页面包含将数据发送到Adobe Analytics所需的最低调用：

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
>您可以通过将`Visitor`的存在分配给[`doPlugins`](/help/implement/vars/functions/doplugins.md)中的自定义变量来跟踪点击是否使用访客ID服务：
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## 使用`s_vi` Cookie识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

如果贵组织未使用访客ID服务，则AppMeasurement将使用其自身的访客识别形式。 当访客首次访问您的网站时，库会检查[`s_vi`](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 此Cookie在匹配[`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md)（对于HTTPS）或[`trackingServer`](/help/implement/vars/config-vars/trackingserver.md)（对于HTTP）的域中设置。

* 如果您参与[托管证书计划](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/adobe-managed-cert)，您的跟踪服务器通常是第一方域，使`s_vi` Cookie成为第一方。
* 如果您未参与托管证书计划，则跟踪服务器通常是`adobedc.net`、`omtrdc.net`或`2o7.net`的子域，从而使`s_vi` Cookie成为第三方Cookie。 由于现代浏览器隐私标准，第三方Cookie被大多数浏览器拒绝。 被拒绝后，AppMeasurement会尝试改为设置第一方回退Cookie (`fid`)。

如果您正确设置`trackingServerSecure`，则无需进一步的访客识别措施。

## 使用`visitorID`识别访客（不推荐）

>[!IMPORTANT]
>
>Adobe建议不要使用此方法来识别访客。

使用[`visitorID`](/help/implement/vars/config-vars/visitorid.md)变量可让您的组织完成识别访客的独立控制。 如果您使用`visitorID`，请注意以下限制：

* 每次点击必须包含相同的`visitorID`值才能计为单个访客。
   * 任何忽略`visitorID`的点击都会自动尝试使用其他访客识别方法，将它们视为单独的访客。
   * 任何包含与上一次点击不同的`visitorID`值的点击都将被视为单独的访客。
   * Adobe不提供在Adobe Analytics中将使用不同访客ID的点击拼合在一起的方法。
* 使用`visitorID`标识的访客不支持共享受众、Analytics for Target和客户属性。

有关使用此变量的实施说明，请参阅[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
