---
description: 此集成将电子邮件营销软件集成反馈系统的强大功能与Adobe Analytics的行为报告结合在一起，为您的组织创建了强大的分析和优化机会。
seo-description: 此集成将电子邮件营销软件集成反馈系统的强大功能与Adobe Analytics的行为报告结合在一起，为您的组织创建了强大的分析和优化机会。
seo-title: optivo® broadmail Data Connector for Adobe Analytics
title: optivo® broadmail Data Connector for Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# optivo® broadmail Data Connector for Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

此集成将电子邮件营销软件集成反馈系统的强大功能与Adobe Analytics的行为报告结合在一起，为您的组织创建了强大的分析和优化机会。

[!DNL ~合作伙伴~] 是一款专业的电子邮件营销软件。 其主要功能是创建、发送和评估新闻稿和电子邮件营销活动。 `[~Partner~]` 提供云服务（软件即服务）。

该集 `[~Partner~]` 成提供了自动化的再营销和数据同步，从而提高了转化率和收入。 该集成使营销人员能够根据客户的电子邮件交互和网站行为自动同步客户细分。 可自定义细分的自动数据交换可帮助您创建极具针对性的电子邮件营销活动，以提升销售，如放弃购物车和将购买后再营销转售到交叉、向上和转售产品。

此集成还交换了从Adobe Analytics到Adobe Analytics的成功电子邮 `[~Partner~]` 件营销活动指标。 关键数据集中显示在电子邮件营销活动概述中。

## 数据连接器实验室计划 {#section-51f9864851b64d96873127b9ac9c9a2b}

此计划是Adobe第三方平台合作伙伴构建集成并将其投放到我们的联合市场的快速跟踪方法。 这些集成功能完全由我们的合作伙伴开发，并在Adobe Experience cloud上按照社区方法提供。 由于集成的第三方性质，这些集成在Adobe Analytics和其他解决方案中的Adobe客户可免费获得，并且按原样提供，且Adobe不提供任何默示担保。

如果您对当前服务、担保人或许可有任何疑问，请与您的Adobe客户经理联系。

## 主要优势和功能{#key-benefits-and-features}

此集成包括以下主要优点：

* 恢复浏览和放弃的购物者
* 通过有针对性的交叉销售和追加销售再营销提高销售额
* 自动基于细分的营销活动
* 优化的营销活动正在进行中
* 合作伙伴中的细 [!DNL ~分~] ，实现目标再营销
* 持续的营销活动指标更新
* 自动化对话触发器

## 动态营销细分{#dynamic-marketing-segments}

此集成具有以下动态营销细分：

* **** 购买配置文件：通过按访客购买模式定向的营销活动增加重复订购和平均订单价值。
* **** 产品／内容查看行为配置文件：根据产品视图和内容访问情况分析，通过营销细分接触潜在客户。
* **** 购物车放弃资料：通过专门为犹豫是否完成购物车的客户设计的优化营销活动，帮助访客转化为客户。
* **** 有效的再营销：客户还可以根据用户的需求创建和计划自定义再营销细分。

## 激活前{#before-you-activate}

在开始与的Data Connectors集成之前，请完成以下要求：

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** 报表包特定：请注意，此集成是特定于报表包的。 在激活集成之前，请确保已选择所需的报表包。
* **** 可用和配置的Adobe Analytics变量：此集成需要自定义事件和自定义eVar。

* **** 委托代理人：请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。 通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **** 消息ID:该集成要求我们在Adobe Analytics变量(eVar)中捕获并存储“消息ID”。 需要这些ID来标识您发送的邮件。 在设置过程中，当向导提示时，您必须为此标识eVar。
* **** 合作伙伴：该集成要求我们在Adobe Analytics变量(eVar) [!UICONTROL ~中捕获和存储~] 一个合作伙伴。 此ID是合作伙伴系统中电子邮件地址的编码或数字 [!UICONTROL ~表示~] 。 此合 [!UICONTROL ~作伙伴~] 与网站上的下游访客行为（购物车放弃、购买等）关联被引入合作伙伴 [!UICONTROL ~系统~] ，并可用于再营销目的。 在设置过程中，当向导提示时，您必须为此标识eVar。
* **** 点击后时间：作为设置过程的一部分，此集成需要向eVar分配与点击后操作的时间相对应的值。 在收件人单击邮件中的链接后，需要将有关收件人 [!UICONTROL ~操作的信息传输~] 给合作伙伴。

* **** 点击后产品：作为设置过程的一部分，此集成需要向eVar分配一个与所提供的与点击后操作关联的产品对应的分配。 在收件人单击邮件中的链接后，需要将有关收件人 [!UICONTROL ~操作的信息传输~] 给合作伙伴。

* **** 点击后操作类型：作为设置过程的一部分，此集成需要为eVar分配一个与点击后操作的类型对应的分配。 在收件人单击邮件中的链接后，需要将有关收件人 [!UICONTROL ~操作的信息传输~] 给合作伙伴。

* **** 隐私合规性：您应该了解，通过启用“收件人”或“访客ID”跟踪功能，可跟踪网站访客的个人身份信息。 这涉及隐私问题，需要贵组织实施适当的程序，例如向网站访客发出通知并征得其同意。

## 定价{#pricing}

请注意，启用此集成可能会导致贵公司根据您与Adobe, Inc.的服务协议或您与Adobe信任的合作伙伴之一的服务协议（如果适用）产生费用。

通过激活此集成，您即表示您是您公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。

### Adobe定价注意事项 {#section-1f4f46c0d969435db57d38c1c310a05a}

Adobe Analytics解决方案的当前客户没有使用此数据连接器集成的额外成本。 尚未转到新Adobe Analytics产品的客户应与其Adobe客户代表联系以获取更多详细信息。

### 合作伙伴定价注意事项 {#section-f8ca71df32224412a5101efb6e356529}

此集成适用于合作伙 [!DNL ~伴客户~] ，但需支付额外的集成费用。 有关定价详细信息，请与sales@optivo.com联系。 请与合作伙 [!DNL ~伴联系~] ，了解定价详细信息。

## Adobe Analytics变量{#adobe-analytics-variables}

此集成需要Adobe Analytics变量来跟踪指标。

在确定要与此集成一起使用的事件和eVar后，必须在Analytics管理控制台中启用它们(有关说明，请参 [阅报表包](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) )。