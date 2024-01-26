---
title: 数据包分析程序
description: 数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。
keywords: 数据包嗅探器、http 状态、200、302、charles
feature: Validation
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 100%

---

# 数据包分析程序

数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。

与 Adobe Experience Cloud 调试器类似，数据包监视工具可以显示在图像请求中传递的数据参数；而同时，数据包监视工具还提供以下附加功能：

* 查看自定义链接跟踪图像请求
* 查看使用 JavaScript 以外的实施方法的图像请求，例如硬编码图像请求或 [!DNL Appmeasurement]

要查看 Analytics 请求，请使用“b/ss”过滤出站请求。

在极少数情况下，该调试程序会报告并未向 Adobe [!DNL Analytics] 处理服务器发送的图像请求。使用数据包监视工具是确保特定图像请求能够成功发送的一种极佳方式。

Adobe 不提供正式的数据包监视工具，但是互联网上存在大量这种程序。以下是其他人发现有用的一些数据包监视工具。

>[!TIP]
>
>这些列表并不完整，只提供了关于常用监视器的信息。

| Firefox | Internet Explorer | Chrome | 独立程序 |
|---|---|---|---|
| [观察点](https://www.observepoint.com/product#plugin)（标记查看器） | [HttpWatch](https://www.httpwatch.com/) | [观察点](https://www.observepoint.com/product#plugin)（标记查看器） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Chrome 开发人员工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>对于您在使用这些数据包监视器时可能遇到的任何问题，Adobe 不提供支持，也不进行故障诊断。请咨询数据包监视器的来源网站，以寻求帮助。

## 典型 HTTP 响应状态代码

当 AppMeasurement 将数据发送到 Adobe 数据收集服务器时，服务器会使用响应状态代码进行响应。

* **200 OK**：来自数据收集服务器的最常见响应。已成功接收图像请求，并返回了透明图像。
* **302 FOUND**：收到此响应的原因有两个：
   * 访客的第一个图像请求：如果用户首次访问您的网站，则会发生重定向。此重定向是为了获取访客 Cookie。它不影响数据收集。
   * Comscore 与 Adobe 集成：如果贵组织使用 Comscore/Analytics 集成，则每个图像请求总会导致 302 响应。
* **404 NOT FOUND**：此响应意味着找不到图像请求，并且数据未发送到 Adobe 数据收集服务器。当硬编码图像请求的格式不正确时，也可能会出现此响应。请与实施 Analytics 的个人或团队合作以解决此问题。

## 响应代码中的 NS_BINDING_ABORTED

出现该消息的原因是，链接跟踪图像请求被设计为允许浏览器在等待 Adobe 数据收集服务器响应之前继续进入下一页。

Adobe 对图像请求的响应只是一个空白的 1x1 像素透明图像，并且该图像与网页的内容无关。如果在 Adobe 提供的数据包监视器中存在行项目，则无论发生 **[!UICONTROL 200 OK]** 响应还是 **[!UICONTROL NS_BINDING_ABORTED]** 响应，相关数据都会到达 Adobe 服务器。无需使页面等候更长时间。

数据包监视器作为一个插件集成到其中，很少看到完整的响应。这些监视器通常会因未收到完整的响应而认为请求被中止。这些监视器很少会区分到底是请求还是响应被中止。独立的数据包监视器通常会提供更详细的消息并可更准确地报告状态。例如，用户可能会收到一则 *Charles* 消息，显示“客户端在接收到完整的响应前已关闭连接”。这表示数据已到达我们的服务器，而浏览器在收到 1x1 像素之前已进入到下一个页面。

如果外部数据包监视器报告数据收集请求被中止，而不是响应被中止，这可能便是问题的原因。Adobe [!DNL Customer Care] 可帮助进行疑难解答。
