---
description: 在进行了所有需要的网站更新之后，您可以使用网络流量查看器（如 Charles*、Chrome 开发人员工具或 Firebug*）来确认 DFA 正在与 Adobe 收集服务器通信。
keywords: DFA
seo-description: 在进行了所有需要的网站更新之后，您可以使用网络流量查看器（如 Charles*、Chrome 开发人员工具或 Firebug*）来确认 DFA 正在与 Adobe 收集服务器通信。
seo-title: 确认 DFA 集成成功
solution: Analytics
title: 确认 DFA 集成成功
topic: Data connectors
uuid: d658cd7c-637-439a-850c-eca8 c41 f970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 确认 DFA 集成成功{#confirming-a-successful-dfa-integration}

在进行了所有需要的网站更新之后，您可以使用网络流量查看器（如 Charles*、Chrome 开发人员工具或 Firebug*）来确认 DFA 正在与 Adobe 收集服务器通信。

在部署启用了 DFA 的 `s_code.js` 文件后，请使用网络流量查看器来查看 DFA 和 Adobe 数据收集服务器之间的请求，进而查找以下内容：

* A request to DFA's `fls.doubleclick.net/json` service. 此服务可做出不同的响应，具体取决于您使用的 DFA 版本。通过 DFA 集成版本 1.5 可以：

   * 到 [!DNL ad.doubleclick.net] 的 HTTP 302 重定向。这将在响应中发送一个 Location: 标识，其中包含有关广告访客的信息。
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. 此服务将有关广告访客的信息转换为 JSON（启用 JavaScript 对象表示法）编码的字符串。将通过一个 200 OK HTTP 响应返回此数据。

* 通过 DFA 集成版本 2.0（启用高级广告服务）可以：

   * [!DNL fls.doubleclick.net] 将通过一个 200 OK 做出直接响应。

在任何一种情况下，一次成功的请求将导致对 Adobe 数据收集服务器的请求，并且该请求中包含参数 vX，其中 X 是您的显示到达 eVar 数。此参数值采取以下格式：DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX。此字符串包含有关当前访客上次点击和上次展示的数据。
