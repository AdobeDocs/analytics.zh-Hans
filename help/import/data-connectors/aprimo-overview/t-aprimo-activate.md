---
description: 使用 Adobe Data Connectors 配置向导来设置集成。
title: 激活集成
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 激活集成 {#activate-the-integration}

使用 Adobe Data Connectors 配置向导来设置集成。

1. 启动 [Data Connectors](https://marketing.adobe.com/resources/help/zh_CN/genesis/c_overview.html)，然后单击 **[!UICONTROL + 新增]**&#x200B;以[添加新集成](https://marketing.adobe.com/resources/help/zh_CN/genesis/t_add_integration.html)。
1. 在&#x200B;**[!UICONTROL 显示]**&#x200B;列表中，选择&#x200B;**[!UICONTROL 按名称]**，然后将 [!DNL ~Partner~] 集成拖至空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 从此集成接收数据的报表包。 |
| 集成名称 | 指定 Data Connectors 在报表包的活动集成列表中显示的集成名称。 |
| 帐户 ID | 指定您的 Aprimo 帐户 ID。 |
| 收件人 ID | 此 ID 是 Aprimo 系统中电子邮件地址的编码或数字表示形式。此“收件人 ID”与提取到 Aprimo 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。 |
| 已点击 | （必需）指定用于存储从电子邮件系统导入的电子邮件点击数据的 Adobe Analytics 事件。“已点击”事件让您能够查看点击了电子邮件的访客数量。 |
| 消息 ID | （必需）存储唯一的邮件 ID。 |
| 已打开 | （必需）指定用于存储从电子邮件系统导入的电子邮件打开数据的 Adobe Analytics 事件。“已打开”事件让您能够查看打开了电子邮件的访客数量。 |
| 收件人 ID | （必需）存储唯一的访客 ID。 |
| 已发送 | （必需）指定用于存储从电子邮件系统导入的电子邮件发送数据的 Adobe Analytics 事件。“已发送”事件让您能够查看已发送的电子邮件数量。 |
| 退回 | （必需）指定用于存储从电子邮件系统导入的电子邮件退回总计数据的 Adobe Analytics 事件。“退回总计”事件让您能够查看由于传输问题而未发送给收件人的电子邮件数量。 |
| 已取消订阅 | （必需）指定用于存储从电子邮件系统导入的电子邮件取消订阅数据的 Adobe Analytics 事件。“已取消订阅”事件让您能够查看以下访客的数量：打开了电子邮件，但随后单击“取消订阅”链接以选择退出接收贵组织今后的电子邮件。 |
| 区段 | 此集成会创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果要使用 s_code.js 插件作为此集成的收集模型，请选择 **JavaScript 插件**。 |
如果要为此集成使用自动收集模型，请选择&#x200B;**自动解决方案**，然后指定用于此集成的唯一标识符。如果选择此选项，请指定用于此集成的唯一标识符：
<ul><li>消息 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的消息 ID。</li>
<li>收件人 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的收件人 ID。</li></ul>|
|功能板和书签生成|自动为集成生成功能板和书签。|
