---
title: Adobe Analytics中的会话疑难解答
description: 了解如何解决与注销Adobe Analytics相关的问题。
seo-title: Adobe Analytics中的会话疑难解答
seo-description: 了解如何解决与注销Adobe Analytics相关的问题。
translation-type: tm+mt
source-git-commit: 5df7bc43587deed41786f6c85f472fb6f908caf8

---


# Adobe Analytics中的会话疑难解答

本页面介绍了会话疑难解答，这意味着您能够成功登录，但有问题需要登录。 如果您在登录Adobe Analytics时遇到问题，请参阅登 [录Adobe Analytics疑难解答](troubleshoot-login.md)。

几乎所有基于会话的问题都源自组织的自定义公司网络。 如果您能够登录到Adobe Analytics，但无法继续登录，请使用本文帮助确定原因。

## 确定问题是否由贵组织的网络造成

许多组织都部署了其他网络功能来增强安全性，如代理服务器或防火墙。 这些自定义有时会干扰在Adobe Analytics中保留活动会话的能力。

要确定您所连接的公司网络是否导致使用Adobe Analytics的问题，请在公司网络外的设备上使用Experience cloud登录凭据。 设备的示例可以通过家庭网络或移动设备的数据计划。 如果您能够在不注销的情况下成功地从页面之间移动到页面，则贵组织的网络可能是您从Adobe Analytics中注销的原因。

## 代理问题

Adobe在向Adobe发出请求时使用授权头。 某些代理(如Bluecoat（现在由赛门铁克拥有）)会删除Adobe Analytics使用的关键授权头信息。 当Adobe看不到授权标题时，会话将过期。

要解决此问题，Adobe建议与贵组织的IT团队合作，以通过贵组织的代理允许授权头。

> [!NOTE] 尽管 Analytics 社区成员发现以下链接很有帮助，但这些链接并不归 Adobe 所有。查看其内容时，请注意这一点。

有关Symantec代理和身份验证头的信息，请访问：

* [在ProxySG或ASG装置上的代理链部署中配置上游代理身份验证](https://support.symantec.com/en_US/article.TECH246122.html)
* [允许ProxySG始终转发服务器授权上游](https://support.symantec.com/en_US/article.TECH244708.html)
