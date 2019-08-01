---
description: '开始数据连接器集成之前，请完成以下要求 '
seo-description: '开始数据连接器集成之前，请完成以下要求 '
seo-title: 在激活之前
title: 在激活之前
uuid: 45275635-a80 d-46c2-b9 ad-985df5737 bf2
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Before You Activate{#before-you-activate}

在启动数据连接器集成之前，请完成以下要求：

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **特定于报告套件：** 建议此集成特定于报告套件。在激活集成之前，请确保您已选择所需的报表包。
* **可用和配置的Adobe Analytics变量：** 此集成需要自定义事件和自定义eVar。See [Adobe Analytics Integration Variables](../../optivo-overview/optivo-requirements/optivo-variables.md#concept-8ebd2bde4a1c4b0aad2987e050ffbbfc).

* **授权代表：** 请注意，此集成的启用可能会导致您的公司根据您与Adobe，Inc或您与Adobe信任的合作伙伴之一的服务协议(如适用)向您的服务协议收取费用。激活此集成表示您是贵公司的授权代表；因此，您的公司同意支付上述服务协议中规定的费用(如果有)。
* **消息ID：** 集成要求我们在Adobe Analytics变量(eVar)内捕获并存储“消息ID”。需要这些ID才能识别您发送的邮件。在设置过程中，您必须在向导提示时为此目的标识eVar。
* ** [!DNL ~Partner~]:** The integration requires that we capture and store a " [!DNL ~Partner~]" within a Adobe Analytics variable (eVar). This ID is an encoded or numeric representation of an email address from the [!DNL ~Partner~] system. This " [!DNL ~Partner~]" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!DNL ~Partner~] system and can be leveraged for remarketing purposes. 在设置过程中，您必须在向导提示时为此目的标识eVar。
* **点击时间：** 在设置过程中，此集成需要为eVar分配一个与点击后操作时间对应的分配。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **Post Click Product：** 在设置过程中，此集成需要分配给与提供的帖子操作关联的提供产品的eVar。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **帖子单击操作类型：** 在设置过程中，此集成需要分配给与点击后操作类型对应的eVar。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **隐私合规性：** 您应当了解，通过启用收件人ID跟踪或访客ID跟踪功能，此功能可跟踪网站访客的个人身份信息。这涉及到隐私事项，需要您的组织实施适当的程序，例如向您的网站访客提供通知和同意。

## Section Title {#section-370f12579a224d509545cba1c28adb22}

