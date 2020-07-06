---
title: 数据包分析程序
description: 数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '534'
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

>[!NOTE]
>
>这些列表并不完整，只提供了关于常用监视器的信息。如果您成功地使用了某数据包监视工具，并且发现它非常有用，请随时使用此窗口右侧的[!UICONTROL 反馈]按钮向我们提供反馈信息。

| Firefox | Internet Explorer | Chrome | 独立程序 |
|---|---|---|---|
| [观察点](https://www.observepoint.com/product#plugin)（标记查看器） | [HttpWatch](https://www.httpwatch.com/) | [观察点](https://www.observepoint.com/product#plugin)（标记查看器） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome 开发人员工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe 不支持或解决您在使用这些数据包监视工具时可能遇到的任何问题。请咨询数据包监视工具的始发网站，以寻求帮助。

## 响应代码中的 NS_BINDING_ABORTED

该错误发生的原因是跟踪图像请求的链接被设计为允许浏览器在等待 Adobe 数据收集服务器响应之前继续进入下一页。

Adobe 对图像请求的响应只是一个空白的 1x1 像素透明图像，并且该图像与网页的内容无关。如果在 Adobe 提供的数据包监视工具中存在行项目，则无论发生 **[!UICONTROL 200 OK]** 响应还是 **[!UICONTROL NS_BINDING_ABORTED]** 响应，相关数据都会到达我们的服务器。无需使页面等候更长时间。

数据包监视器作为一个插件集成到其中，很少看到完整的响应。这些监视器通常会因未收到完整的响应而认为请求被中止。这些监视器很少会区分到底是请求还是响应被中止。独立的数据包监视器通常会提供更详细的消息并可更准确地报告状态。例如，用户可能会收到一则 *Charles* 消息，显示“客户端在接收到完整的响应前已关闭连接”。这表示数据已到达我们的服务器，而浏览器在收到 1x1 像素之前已进入到下一个页面。

如果外部数据包探查器报告数据搜集请求被中止，而不是响应被中止，这可能便是问题的原因。Adobe [!DNL Customer Care] 可帮助进行疑难解答。
