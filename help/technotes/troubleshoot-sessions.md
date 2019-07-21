---
title: Adobe Analytics中的会话疑难解答
description: 了解如何解决从Adobe Analytics注销的问题。
seo-title: Adobe Analytics中的会话疑难解答
seo-description: 了解如何解决从Adobe Analytics注销的问题。
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# Adobe Analytics中的会话疑难解答

本页与疑难解答会话有关，这意味着您能够成功登录，但仍有问题登录。If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

几乎所有基于会话的问题都源自组织的自定义企业网络。如果您能够登录Adobe Analytics但无法登录，请使用本文来帮助确定原因。

## 确定问题是否由您的组织的网络造成

许多组织部署额外的网络功能以增强安全性，如代理服务器或防火墙。这些自定义有时会干扰在Adobe Analytics中保留活动会话的能力。

要确定您连接的企业网络是否正在导致使用Adobe Analytics，请在企业网络之外的设备上使用Experience Cloud登录凭据。设备示例可通过家庭网络或移动设备的数据计划进行。如果您能够成功地逐页移动到页面，而不注销，则您的组织网络可能是您注销Adobe Analytics的原因。

## IP池导致的问题

一些网络使用称为IP池的练习，其中设备的IP地址在单位使用的范围内经常发生变化。作为Adobe安全实践的一部分，如果IP地址更改中间会话，则该会话将过期。

如果您的单位使用IP池，请使用以下说明将您的IP范围添加到Adobe的白名单中：

1. 与组织的IT团队合作，获取组织中使用的IP范围列表
2. 由客户支持代表联系Adobe客户服务中心并向Adobe提供IP范围
3. 代理将IP范围输入白名单中，以防止会话在提供的范围内时过期

## 代理应存在的问题

Adobe在向Adobe提出请求时使用授权标题。一些代理(如Bluecoat(现在由赛门铁克拥有)简化了Adobe Analytics使用的关键授权标题信息。当Adobe看不到授权标题时，会话已过期。

为了解决此问题，Adobe建议您与组织的IT团队合作，允许授权标题通过单位的代理进行授权。

> [!NOTE] 注释
>
> 尽管Analytics社区成员发现以下链接有用，但并非Adobe拥有。查看其内容时，请考虑此备注。

有关Symantec代理和身份验证标题的信息，可在以下位置找到：

* [在ProxiSG或ASG Appliance上的代理链部署中配置上游代理身份验证](https://support.symantec.com/en_US/article.TECH246122.html)
* [允许Proxix始终在上游转发服务器授权](https://support.symantec.com/en_US/article.TECH244708.html)
