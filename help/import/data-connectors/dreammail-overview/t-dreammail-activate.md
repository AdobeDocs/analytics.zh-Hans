---
description: 使用Adobe Data Connectors配置向导设置集成。
title: 激活集成
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
| 集成UUID | 指定DreamMail集成UUID。 |
| 客户端名称 | 指定您的DreamMail客户端名称。 |
| 网站名称 | 指定您的DreamMail站点名称。 |
| 回弹 | 由于传送问题而未传送给收件人的电子邮件数。 |
| 交付 | 成功发送消息的数量。 |
| 交付错误 | 消息传送失败。 |
| HTML打开 | 打开电子邮件的访客数。 |
| 无效者 | 无效电子邮件地址数。 |
| 促销活动 | 营销活动ID。 |
| Pass Alongs | 通过“已点击”事件，您可以查看点击电子邮件的访客数。 |
| Email eVar | DreamMail系统的电子邮件地址。 此“电子邮件eVar”与网站上的下游访客行为（购物车放弃、购买等）相关联它被引入DreamMail系统，并可用于再营销目的。 |
| 聚焦事件 | 可在再营销区段中导出的事件。 |
| 精选购买 | 可在再营销区段中导出的事件。 |
| 聚光灯值 | 可在再营销区段中导出的收入事件。 |
| TotalClicks | 通过“已点击”事件，您可以查看点击电子邮件的访客数。 |
| 区段 | 此集成创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。 此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果 **要使用s_code.js插件作为此集成的集合模型** ，请选择“JavaScript插件”（请参阅）。 如果 **要为此集成使用自动收集模型** ，请选择自动化解决方案，然后指定用于此集成的唯一标识符。 如果选择此选项，请指定用于此集成的唯一标识符：<ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面URL的消息ID。</li><li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。</li></ul> |
| 功能板和书签生成 | 自动生成功能板和书签以进行集成。 |
