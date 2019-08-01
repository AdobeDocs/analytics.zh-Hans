---
description: 使用Adobe数据连接器配置向导设置集成。
seo-description: 使用Adobe数据连接器配置向导设置集成。
seo-title: 激活集成
title: 激活集成
uuid: 93c59f8e-3cf5-44c1-9a04-2260af93d5d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

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
| Clicked | 电子邮件点击总数。 |
| 促销活动 ID | 存储唯一消息ID。这通常存储在营销活动变量中。 |
| 已打开 | 打开的电子邮件总数。 |
| 人物点击 | 单击的人数。 |
| 已处理 | 处理的电子邮件总数。 |
| Broadlog ID | 此ID是Neolane系统中电子邮件地址的编码或数字表示形式。此“Broadlog ID”与网站上的下游访客行为相关(购物车ID放弃、购买等)它被引入Neolane系统中，并可用于再营销用途。 |
| 已计划 | 计划交付的电子邮件数。 |
| 已发送 | 发送的电子邮件数。 |
| 退回总次数 | 由于交付问题而未发送给收件人的电子邮件数。 |
| 唯一点击数 | 不同点击数。 |
| 唯一打开 | 打开的数量。 |
| 取消订阅 | 打开电子邮件的访客数，但然后单击取消订阅链接，以退出单位将来的电子邮件消息。 |
| 区段 | 此集成可创建合作伙伴定义区段中显示的合作伙伴定义区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用推荐的访问权限。 |
| 数据收集 | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. 如果选择此选项，则指定用于此集成的唯一标识符： <ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加给登陆页面URL的消息ID。</li><li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴的登录页面URL的收件人ID附加。</li></ul> |
| 控制板和书签生成 | 自动生成集成的仪表板和书签。 |