---
description: 此 Adobe® Data Connectors™ 电子邮件集成将 Adobe Analytics® 中的行为信息与电子邮件营销整合在一起，创建出一款功能强大的工具，通过更相关的消息传送来重新定义成功衡量指标和目标受众。
title: 适用于 Adobe Analytics 的 Aprimo Data Connector
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 98%

---


# 适用于 Adobe Analytics 的 Aprimo Data Connector{#aprimo-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将在2021年中后期终止Adobe Data Connector技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

此 Adobe® Data Connectors™ 电子邮件集成将 Adobe Analytics® 中的行为信息与电子邮件营销整合在一起，创建出一款功能强大的工具，通过更相关的消息传送来重新定义成功衡量指标和目标受众。

向这些市场区段发送相关电子邮件，可能会带来全新的收入契机，从而在新电子邮件促销活动和现有电子邮件促销活动中提高转化率和收入。例如，经证实，根据访问期间查看的产品或放弃购买的产品发送相关电子邮件，可对收入产生显著影响，并且对成本的影响最小，因为这只是利用网站已获取的访客。

提高营销效率，是 [!DNL Adobe Analytics] 与 Aprimo 集成的主要优势之一。此外，此集成会自动将电子邮件量度与 [!DNL Adobe Analytics] 数据同步（频率为每小时一次），以实现闭环报告。

## 主要优势和功能{#key-benefits-and-features}

此集成具有以下主要优势：

* 将电子邮件营销数据与 Analytics 数据整合到一个报表界面中。
* 通过转化为收入和促进网站取得成功，优化电子邮件促销活动。
* 根据动态营销区段，向关键访客和市场区段进行再营销。

## 动态营销区段{#dynamic-marketing-segments}

此集成具有以下动态营销区段：

* **购买配置文件：**&#x200B;通过按访客购买模式定位的促销活动，增加重复订单和提高平均订单价值。
* **产品/内容查看行为配置文件：**&#x200B;通过基于产品查看和内容访问分析的营销区段，吸引潜在客户。
* **放弃购买配置文件：**&#x200B;通过专门针对那些犹豫是否要完成购物的访客而设计的优化促销活动，帮助将这些访客转化为客户。
* 客户还可以专门针对其用户需求创建和计划自定义再营销区段。

## 激活前{#before-you-activate}

在启动 Data Connectors 集成之前，请完成以下要求：

### Adobe Analytics 要求 {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **特定于报表包：**&#x200B;请注意，此集成特定于报表包。在激活集成之前，请确保已选择所需的报表包。
* **已配置的可用 Adobe Analytics 变量：**&#x200B;此集成需要自定义事件和自定义 eVar，以及可选的其他事件和其他 eVar。
* **授权代表：**&#x200B;请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。
* **Data Warehouse™：**&#x200B;此集成要求启用 Data Warehouse 以生成再营销区段。如果尚未启用 Data Warehouse，请联系 Adobe 以了解详细信息。
* **[!UICONTROL Partner~]：**此集成要求我们捕获“[!DNL ~Partner~]”并将其存储在一个 Adobe Analytics 变量 (eVar) 中。此 ID 是[!DNL ~Partner~]系统中电子邮件地址的编码或数字表示形式。此“[!DNL ~Partner~]”与提取到[!DNL ~Partner~]系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。在设置过程中，当收到向导提示时，您必须为此确定一个 eVar。
* **外部跟踪：**&#x200B;如果您当前没有遵循为您发送的每个电子邮件促销活动启用外部跟踪这一最佳实践，则必须这样做以确保成功集成。有关详细信息，请参阅下面的 [!DNL ~Partner~] 部分。
* **隐私合规：**&#x200B;您应该了解，启用“收件人 ID”或“访客 ID”跟踪功能，即表示该功能可能会跟踪您网站访客的个人身份信息。这会涉及隐私问题，需要贵组织实施适当的规程，例如，向网站访客发出通知并征得其同意。

## 定价{#pricing}

请注意，根据您与 Adobe, Inc. 的服务协议或您与 Adobe 信任的某一合作伙伴的服务协议（如果适用），启用此集成可能会导致向贵公司收取相关费用。

激活此集成，即表示您是贵公司的授权代表；因此，贵公司同意支付上述服务协议中规定的费用（如有）。

### Adobe 定价注意事项 {#section-1f4f46c0d969435db57d38c1c310a05a}

可能会产生与此集成相关的经常性费用和实施费用，包括通过此集成产生的增加服务器调用次数的成本。有关定价详细信息，请联系您的 Adobe 客户代表。

### ~Partner~ 定价注意事项 {#section-f8ca71df32224412a5101efb6e356529}

可能会产生与此集成相关的经常性费用和实施费用。有关定价详细信息，请联系 [!DNL ~Partner~]。

## Adobe Analytics 变量{#adobe-analytics-variables}

此集成需要 Adobe Analytics 变量才能跟踪量度。

在确定要与此集成一起使用的事件和 eVar 后，必须在 Adobe Analytics Admin Console 中启用它们（有关说明，请参阅[报表包](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/manage-report-suites/report-suites-admin.html)）。
