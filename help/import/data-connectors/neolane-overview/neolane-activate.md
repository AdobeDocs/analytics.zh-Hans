---
description: 使用 Adobe Data Connectors 配置向导来设置集成。
title: 激活集成
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 激活集成{#activate-the-integration}

使用 Adobe Data Connectors 配置向导来设置集成。

1. Start [Data Connectors](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://docs.adobe.com/content/help/en/analytics/import/dataconnectors/getting-started-data-connectors.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 从此集成接收数据的报表包。 |
| 集成名称 | 指定 Data Connectors 在报表包的活动集成列表中显示的集成名称。 |
| 已点击 | 电子邮件总点击次数。 |
| 促销活动 ID | 存储唯一消息 ID。它通常存储在促销活动变量中。 |
| 已打开 | 电子邮件总打开次数。 |
| 人员点击 | 点击的人数。 |
| 已处理 | 已处理的电子邮件总数。 |
| Broadlog ID | 此 ID 是 Neolane 系统中电子邮件地址的编码或数字表示形式。此“Broadlog ID”与提取到 Neolane 系统中的网站下游访客行为（Broadlog ID 放弃购买、购买等）相关联，且可用于再营销。 |
| 已计划 | 计划发送的电子邮件数量。 |
| 已发送 | 已发送的电子邮件数量。 |
| 退回总计 | 由于传输问题而未发送给收件人的电子邮件数量。 |
| 唯一点击次数 | 非重复点击的次数。 |
| 唯一打开次数 | 非重复打开的次数。 |
| 已取消订阅 | 打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后电子邮件的访客数量。 |
| 区段 | 此集成会创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果要使用 s_code.js 插件作为此集成的收集模型，请选择 **JavaScript 插件**。如果要为此集成使用自动收集模型，请选择&#x200B;**自动解决方案**，然后指定用于此集成的唯一标识符。如果选择此选项，请指定用于此集成的唯一标识符： <ul><li>消息 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的消息 ID。</li><li>收件人 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的收件人 ID。</li></ul> |
| 功能板和书签生成 | 自动为集成生成功能板和书签。 |
