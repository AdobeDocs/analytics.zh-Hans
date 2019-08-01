---
description: 介绍成功集成的先决条件。
seo-description: 介绍成功集成的先决条件。
seo-title: 集成先决条件
solution: Analytics
title: 集成先决条件
uuid: ac93bf4d-a071-4fac-9d42-c4856463 cbb6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Integration Prerequisites{#integration-prerequisites}

介绍成功集成的先决条件。

在激活此集成之前，请根据您的Adobe Analytics和电子邮件软件部署情况检查下列项目。

这可以确保在激活之前适当的最佳实践和先决条件，从而实现最佳、成功的集成。

## Prerequisites for Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **特定于报告包**：请注意，此集成特定于报告套件。在激活集成之前，请确保您已选择所需的报告套件
* **可用和配置的Analytics变量**：此集成需要自定义事件和自定义eVar，以及可选的其他事件和其他eVar。

   See [Configure Analytics variables for Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **授权代表**：请注意，此集成的启用可能会导致您的公司根据您与Adobe，Inc或您与Adobe信任的合作伙伴之一的服务协议(如适用)向您的服务协议收取费用。激活此集成表示您是贵公司的授权代表；因此，您的公司同意支付上述服务协议中规定的费用(如果有)。
* **Adobe Analytics数据仓库**：此集成需要启用Adobe Analytics数据仓库才能生成重新营销区段。如果尚未启用数据仓库，请与Adobe联系以获取详细信息。
* **收件人ID**：集成要求我们在Analytics变量(eVar)内捕获并存储“访客ID”。访客ID(通常称为“收件人ID”)是来自Lyris系统的电子邮件地址的编码或数字表示形式。此“收件人ID”与网站上下游访客行为相关(购物车放弃、购买等)它被移回Lyris系统中，并可用于重新营销用途。在设置过程中，您必须在向导提示时为此目的标识eVar。
* **外部跟踪**：如果当前未遵循为每个电子邮件营销活动启用外部跟踪的最佳实践，则必须确保成功集成。请参见下面的Lynris部分了解详细信息
* **隐私合规性**：您应当了解，通过启用收件人ID跟踪或访客ID跟踪功能，此功能可跟踪网站访客的个人身份信息。这具有隐私意义，需要您的组织实施适当的程序，例如向您的网站访客提供通知和同意。

## Prerequisites for Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **有效的Lyris帐户**：要使用此数据连接器集成，您必须具有有效的Lyris帐户。
* **帐户信息**：在此集成设置期间，您将需要有关您的Lyris帐户的以下信息：

   * *Lyris API密钥*：用于数据人群
   * *查询字符串参数*：这些内容附加到消息ID和收件人ID(访问者ID)的登录页面URL中。
   * *Lyris Server/URL*：您在Lyris系统中使用的服务器值
   * *Lyris Site ID*：这也称为“客户ID”，它是您的Lynris HQ实例的唯一值。它位于EmailLabs的“帐户主页”部分“客户信息”下。

