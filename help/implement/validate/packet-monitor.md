---
title: 数据包分析程序
description: 数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。
keywords: 数据包嗅探器、http 状态、200、302、charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 679
ht-degree: 71%

---

# 数据包分析程序

数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。

与 Adobe Experience Cloud 调试器类似，数据包监视工具可以显示在图像请求中传递的数据参数；而同时，数据包监视工具还提供以下附加功能：

* 查看自定义链接跟踪图像请求
* 查看使用 JavaScript 以外的实施方法的图像请求，例如硬编码图像请求或 [!DNL Appmeasurement]

要查看 Analytics 请求，请使用“b/ss”过滤出站请求。

在极少数情况下，该调试程序会报告并未向 Adobe [!DNL Analytics] 处理服务器发送的图像请求。 使用数据包监视器是一种很好的方法，可以100%确保成功触发特定图像请求。

虽然Adobe不提供正式的数据包监视器，但它们在互联网上却有着广泛的用途。 下面是一些其他设备认为有用的数据包监视程序。

>[!TIP]
>
>这些列表并不完整，只提供了关于常用监视器的信息。

| Firefox | Internet Explorer | Chrome | 独立程序 |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) （标记查看器） | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) （标记查看器） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome 开发人员工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.telerik.com/fiddler) |
| [篡改数据](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>对于您在使用这些数据包监视器时可能遇到的任何问题，Adobe 不提供支持，也不进行故障诊断。 请咨询数据包监视器的来源网站，以寻求帮助。

## 典型 HTTP 响应状态代码

当 AppMeasurement 将数据发送到 Adobe 数据收集服务器时，服务器会使用响应状态代码进行响应。

* **200 OK**：来自数据收集服务器的最常见响应。 已成功接收图像请求，并返回了透明图像。
* **302 FOUND**：收到此响应的原因有两个：
   * 访客的第一个图像请求：如果用户首次访问您的网站，则会发生重定向。 此重定向是为了获取访客 Cookie。 它不影响数据收集。
   * Comscore 与 Adobe 集成：如果贵组织使用 Comscore/Analytics 集成，则每个图像请求总会导致 302 响应。
* **404 NOT FOUND**：此响应意味着找不到图像请求，并且数据未发送到 Adobe 数据收集服务器。 当硬编码图像请求的格式不正确时，也可能会出现此响应。 请与实施 Analytics 的个人或团队合作以解决此问题。

## 响应代码中的 NS_BINDING_ABORTED

出现该消息的原因是，链接跟踪图像请求被设计为允许浏览器在等待 Adobe 数据收集服务器响应之前继续进入下一页。

Adobe 对图像请求的响应只是一个空白的 1x1 像素透明图像，并且该图像与网页的内容无关。 如果在 Adobe 提供的数据包监视器中存在行项目，则无论发生 **[!UICONTROL 200 OK]** 响应还是 **[!UICONTROL NS_BINDING_ABORTED]** 响应，相关数据都会到达 Adobe 服务器。 无需再等待页面。

作为插件集成的数据包监视器很少看到完整的响应。 他们往往认为请求已中止，因为未收到完整响应。 这些监测器也很少区分是请求还是响应被中止。 独立的数据包监视器通常具有更详细的消息并更准确地报告状态。 例如，用户可能会在&#x200B;*Charles*&#x200B;中收到一条消息，显示“客户端在收到整个响应之前已关闭连接”。 这意味着数据确实到达了我们的服务器，只是浏览器在收到1x1像素之前移动到下一页。

如果外部数据包监视器报告数据收集请求被中止，而不是响应被中止，这可能便是问题的原因。 Adobe [!DNL Customer Care] 可帮助进行疑难解答。
