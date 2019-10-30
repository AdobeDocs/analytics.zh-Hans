---
description: 使用Adobe Data Connectors配置向导设置集成。
seo-description: 使用Adobe Data Connectors配置向导设置集成。
seo-title: 激活集成
title: 激活集成
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 激活集成{#activate-the-integration}

使用Adobe Data Connectors配置向导设置集成。

1. 启动 [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) ，然后单击 **[!UICONTROL +添加新]** , [以添加新集成](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在“显 **[!UICONTROL 示]** ”列表中，选择“按名 **[!UICONTROL 称]** ”，然后将 [!DNL ~Partner~] integration拖至空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 从此集成接收数据的报表包。 |
| 集成名称 | 指定数据连接器在报表包的“活动集成列表”中显示的集成名称。 |
| 已单击 | 电子邮件点击总数。 |
| 促销活动 ID | 存储唯一消息ID。 这通常存储在系列活动变量中。 |
| 已打开 | 打开的电子邮件总数。 |
| 人物点击 | 点击人数。 |
| 已处理 | 已处理电子邮件的总数。 |
| Broadlog ID | 此ID是Neolane系统中电子邮件地址的编码或数字表示形式。 此“Broadlog ID”与站点上的下游访客行为（购物车Broadlog ID放弃、购买等）相关联被引入Neolane系统，并可用于再营销目的。 |
| 已计划 | 计划发送的电子邮件数。 |
| 已发送 | 发送的电子邮件数。 |
| 总弹回次数 | 由于传送问题而未传送给收件人的电子邮件数。 |
| 唯一点击 | 不同点击次数。 |
| 唯一打开次数 | 不同打开次数。 |
| 取消订阅 | 打开电子邮件但随后单击“取消订阅”链接以选择退出您组织将来的电子邮件的访客数。 |
| 区段 | 此集成创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。 此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
|  访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果 **** 要使用s_code.js插件作为此集成的集合模型，请选择“JavaScript插件”。 如果 **要为此集成使用自动收集模型** ，请选择自动化解决方案，然后指定用于此集成的唯一标识符。 如果选择此选项，请指定用于此集成的唯一标识符： <ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面URL的消息ID。</li><li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。</li></ul> |
| 功能板和书签生成 | 自动生成功能板和书签以进行集成。 |
