---
title: Adobe Analytics 中的会话疑难解答
description: 了解如何解决与注销 Adobe Analytics 相关的问题。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics 中的会话疑难解答

本页面介绍会话疑难解答，这意味着您能够成功登录，但是在保持登录状态时出现问题。如果您在登录 Adobe Analytics 时遇到问题，请参阅[登录 Adobe Analytics 疑难解答](troubleshoot-login.md)。

几乎所有基于会话的问题都源自组织的自定义公司网络。如果您能够登录到 Adobe Analytics，但是无法保持登录状态，请使用本文帮助确定原因。

## 确定问题是否由贵组织的网络所造成

许多组织都部署了其他网络功能来增强安全性，如代理服务器或防火墙。这些自定义有时会干扰在 Adobe Analytics 中保留活动会话的能力。

要确定您所连接的公司网络是否导致使用 Adobe Analytics 时出现问题，请在公司网络外部的设备上使用 Experience Cloud 登录凭据。示例设备可以采用家庭网络或移动设备的数据计划。如果您能够在不注销的情况下成功地在页面之间切换，则贵组织网络可能是导致从 Adobe Analytics 中注销的原因。

## 代理问题

向 Adobe 发出请求时 Adobe 使用授权标头。某些代理，如 Bluecoat（现由 Symantec 拥有），会删除 Adobe Analytics 使用的关键授权标头信息。当 Adobe 看不到授权标头时，会话将过期。

要解决此问题，Adobe 建议与贵组织的 IT 团队合作，以允许授权标头通过贵组织的代理。

> [!NOTE] 尽管 Analytics 社区成员发现以下链接很有帮助，但这些链接并不归 Adobe 所有。查看其内容时，请注意这一点。

有关 Symantec 代理和身份验证标头的信息，请访问：

* [在 ProxySG 或 ASG 设备上的代理链部署中配置上游代理身份验证](https://support.symantec.com/zh_CN/article.TECH246122.html)
* [允许 ProxySG 始终转发服务器授权上游](https://support.symantec.com/zh_CN/article.TECH244708.html)
