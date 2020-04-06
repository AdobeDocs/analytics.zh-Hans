---
title: 数据包分析程序
description: 数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 数据包分析程序

数据包分析程序允许您查看由实施发送至 Adobe 数据收集服务器的数据。

与 Adobe Experience Cloud 调试器类似，数据包监视工具可以显示在图像请求中传递的数据参数；而同时，数据包监视工具还提供以下附加功能：

* 查看自定义链接跟踪图像请求
* 查看使用 JavaScript 以外的实施方法的图像请求，例如硬编码图像请求或 [!DNL Appmeasurement]

要查看 Analytics 请求，请使用“b/ss”过滤出站请求。

在极少数情况下，该调试程序会报告并未向 Adobe [!DNL Analytics] 处理服务器发送的图像请求。使用数据包监视器是确保特定图像请求成功触发的绝佳方法。

虽然Adobe不提供正式数据包监视器，但Internet上有各种数据包监视器。 以下是一些其他数据包监视器发现有用的信息。

>[!NOTE]这些列表并不完整，只提供了关于常用监视器的信息。如果您有一个数据包监视器，并且成功使用并发现它很有用，请随时使用此窗口右 [!UICONTROL Feedback] 侧的按钮提供反馈。

| Firefox | Internet Explorer | Chrome | 独立项目 |
|---|---|---|---|
| [观察点](https://www.observepoint.com/product#plugin) （标记查看器） | [HttpWatch](https://www.httpwatch.com/) | [观察点](https://www.observepoint.com/product#plugin) （标记查看器） | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome 开发人员工具](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [篡改数据](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]Adobe 不支持或解决您在使用这些数据包监视工具时可能遇到的任何问题。请咨询数据包监视工具的始发网站，以寻求帮助。

## 响应代码中的 NS_BINDING_ABORTED

出现此错误是因为链接跟踪图像请求旨在让浏览器在等待Adobe数据收集服务器的响应之前继续到下一页。

Adobe对图像请求的响应只是一个空白的1x1透明图像，与页面内容无关。 如果在 Adobe 提供的数据包监视工具中存在行项目，则无论发生 **[!UICONTROL 200 OK]** 响应还是 **[!UICONTROL NS_BINDING_ABORTED]** 响应，相关数据都会到达我们的服务器。无需再等待页面。

作为插件集成的数据包监视器很少看到完整的响应。 由于未收到完全响应，他们倾向于将请求视为已中止。 这些监视器很少区分是请求还是响应被中止。 独立的数据包监视器通常具有更详细的消息，并更准确地报告状态。 例如，用户可能在 *Charles* 中收到一条消息，说“客户端在接收整个响应之前已关闭连接”。 这意味着数据确实到达了我们的服务器，只是浏览器在收到1x1像素之前移到了下一页。

如果外部数据包嗅探器报告数据收集请求被中止，而不是响应，这是令人担心的原因。 Adobe [!DNL Customer Care] 可帮助进行疑难解答。
