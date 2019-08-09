---
description: 使用Adobe数据连接器配置向导设置集成。
seo-description: 使用Adobe数据连接器配置向导设置集成。
seo-title: 激活集成
title: 激活集成
uuid: 9084b691-291d-49f7-9fa4-abda507 e060 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 激活集成{#activate-the-integration}

使用Adobe数据连接器配置向导设置集成。

1. 启动 [数据连接器](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) 并单击 **[!UICONTROL +添加新]** 功能以 [添加新集成](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在 **[!UICONTROL 显示]** 列表中，选择 **[!UICONTROL 按名称]** ，然后将 [!DNL ~合作伙伴~] 集成拖动到空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 接收此集成中的数据的报表包。 |
| 集成名称 | 指定数据连接器显示在报表包的活动集成列表中的集成名称。 |
| 集成UUID | 指定DreamMail Integration UUID。 |
| 客户端名称 | 指定DreamMail客户端名称。 |
| 网站名称 | 指定DreamMail站点名称。 |
| 回弹回弹 | 由于交付问题而未发送给收件人的电子邮件数。 |
| 已交付 | 成功发送邮件的次数。 |
| 交付错误 | 发送失败的邮件。 |
| HTML打开 | 打开电子邮件的访客数。 |
| 别名 | 无效的电子邮件地址数。 |
| 促销活动 | 营销活动ID。 |
| 传递长时间 | 单击“单击”事件可查看单击该电子邮件的访客的数量。 |
| Email eVar | 来自DreamMail系统的电子邮件地址。此“电子邮件eVar”与网站上的下游访客行为相关(购物车放弃、购买等)它被引入DreamMail系统中，并可利用它进行再营销。 |
| 聚焦事件 | 可在重新营销细分中导出的事件。 |
| 亮点购买 | 可在重新营销细分中导出的事件。 |
| 聚光灯值 | 可在重新营销细分中导出的收入事件。 |
| TotalClick | 单击“单击”事件可查看单击该电子邮件的访客的数量。 |
| 区段 | 此集成可创建合作伙伴定义区段中显示的合作伙伴定义区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用推荐的访问权限。 |
| 数据收集 | 如果 **要使用s_ code. js** 插件作为此集成的集合模型(请参阅)，请选择JavaScript插件。如果您要将自动收集模型用于此集成，请选择 **“自动解决方案** ”，然后指定用于此集成的唯一标识符。如果选择此选项，则指定用于此集成的唯一标识符：<ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加给登陆页面URL的消息ID。</li><li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴的登录页面URL的收件人ID附加。</li></ul> |
| 控制板和书签生成 | 自动生成集成的仪表板和书签。 |