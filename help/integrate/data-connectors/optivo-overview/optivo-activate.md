---
description: 使用Adobe数据连接器配置向导设置集成。
seo-description: 使用Adobe数据连接器配置向导设置集成。
seo-title: 激活集成
title: 激活集成
uuid: b2acdb8-9a1f-4f17-92f2-6a3780a8f626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d10546972c03efae1bc365b7391000a40a79b0a4

---


# Activate the Integration{#activate-the-integration}

使用Adobe数据连接器配置向导设置集成。

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 接收此集成中的数据的报表包。 |
| 集成名称 | 指定数据连接器显示在报表包的活动集成列表中的集成名称。 |
| 电子邮件地址 | 提供电子邮件地址以接收集成相关信息。 |
| 帐户ID | 这是电子邮件服务提供商为您的组织分配的唯一标识符。将在请求电子邮件系列数据(例如# Sended、# Opened、# Clicked等)时使用它。将访客区段发送给您的电子邮件服务提供商。 |
| Recipient ID | 此ID是optivo® Broadmail系统中电子邮件地址的编码或数字表示形式。此“收件人ID”与网站上下游访客行为相关(购物车放弃、购买等)它被引入optivo® Broadmail系统，并可利用它进行再营销。 |
| 消息ID | (必需)存储唯一邮寄ID。These classification dimensions are created by the Data Connectors wizard for the Message ID: a)**Campaigns**: Campaigns associated with the message. b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". c)**Country Code**: This field contains the country code of the origin sender country. 它是常数“DE”。d) **Delivery Tool**: Method of transmission, always "Email". e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. f) **Start Date**: Timestamp of the start of this mailing. |
| 点击时间后 | (必需)在收件人单击邮寄中的链接后，需要将收件人操作的相关信息传输到optivo® Broadmail。 |
| Post Click Product | (必需)在收件人单击邮寄中的链接后，需要将收件人操作的相关信息传输到optivo® Broadmail。 |
| 帖子点击操作 | (必需)在收件人单击邮寄中的链接后，需要将收件人操作的相关信息传输到optivo® Broadmail。 |
| 硬回弹 | (必需)指定Adobe Analytics事件，该事件存储从电子邮件系统导入的弹回数据。未发送给收件人的电子邮件数量，被视为永久无法交付。 |
| 柔和回弹 | (必需)指定Adobe Analytics事件，该事件存储从电子邮件系统导入的软弹回数据。由于交付问题而未发送给收件人的电子邮件数。 |
| Clicked | (必需)指定用于存储通过电子邮件系统发送的电子邮件地址的Adobe Analytics事件。单击“单击”事件可查看单击该电子邮件的访客的数量。 |
| 已打开 | (必需)指定用于存储从电子邮件系统中导入的电子邮件打开数据的Adobe Analytics事件。打开的活动可让您查看打开电子邮件的访客的数量。 |
| 已发送 | (必需)指定用于存储通过电子邮件系统导入的电子邮件的Adobe Analytics事件。通过“发送的活动”，可以查看发送的电子邮件的数量。 |
| 取消订阅 | (必需)指定用于存储从电子邮件系统中导入的电子邮件取消订阅数据的Adobe Analytics事件。通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 |
| 区段 | 使现有区段与此集成结合使用(可选)。 |
| 访问请求 | 启用推荐的访问权限。 |
| 数据收集 | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. 如果选择此选项，则指定用于此集成的唯一标识符：<ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的消息ID。</li><li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴的登录页面URL的收件人ID附加。</li></ul> |
| 控制板和书签生成 | 自动生成集成的仪表板和书签。 |