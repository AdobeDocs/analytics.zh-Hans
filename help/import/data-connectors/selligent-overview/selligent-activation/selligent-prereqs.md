---
description: 列出在部署集成之前要参加Adobe Analytics的必要操作。
seo-description: 列出在部署集成之前要参加Adobe Analytics的必要操作。
seo-title: Adobe Analytics先决条件
solution: Analytics
title: Adobe Analytics先决条件
uuid: d799420d-7b06-4086-a6 c6-18971296876c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Adobe Analytics先决条件{#prerequisites-for-adobe-analytics}

列出在部署集成之前要参加Adobe Analytics的必要操作。

| 先决条件 | 注释 |
|---|---|
| 选择报表包 | 请注意，此集成特定于报告套件。在激活集成之前，请确保您已选择所需的报表包。 |
| 配置Analytics变量 | 此集成需要自定义事件和自定义eVar，以及可选的其他事件和其他eVar。请参阅为Seligent配置Analytics变量。 |
| 授权代表 | 请注意，此集成的启用可能会导致您的公司根据您与Adobe，Inc或您与Adobe信任的合作伙伴之一的服务协议(如适用)向您的服务协议收取费用。激活此集成表示您是贵公司的授权代表；因此，您的公司同意支付上述服务协议中规定的费用(如果有)。 |
| 启用Adobe Data Warehouse™ | 此集成需要启用数据仓库才能生成再营销区段。如果尚未启用Adobe数据仓库，请与Adobe联系以获取详细信息。 |
| Recipient ID | 集成要求我们在Analytics变量(eVar)内捕获并存储“访客ID”。访客ID(通常称为“收件人ID”)是来自Seligent系统的电子邮件地址的编码或数字表示形式。此“收件人ID”与网站上下游访客行为相关(购物车放弃、购买等)它被移回到Selligent系统中，并可用于再营销用途。在设置过程中，您必须在向导提示时为此目的标识eVar。 |
| 外部跟踪 | 如果当前还没有遵循为每个电子邮件营销活动启用外部跟踪的最佳实践，则必须确保成功集成。有关详细信息，请参阅下面的“Seriglent”部分。 |
| 隐私合规性 | 您应当了解，通过启用收件人ID跟踪或访客ID跟踪功能，此功能可跟踪网站访客的个人身份信息。这涉及到隐私事项，需要您的组织实施适当的程序，例如向您的网站访客提供通知和同意。 |

