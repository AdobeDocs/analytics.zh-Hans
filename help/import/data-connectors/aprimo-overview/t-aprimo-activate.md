---
description: 使用Adobe数据连接器配置向导设置集成。
seo-description: 使用Adobe数据连接器配置向导设置集成。
seo-title: 激活集成
title: 激活集成
uuid: 0a5d4d45-5133-4259-96ce-c992 a1 e314 ee
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 激活集成 {#activate-the-integration}

使用Adobe数据连接器配置向导设置集成。

1. 启动 [数据连接器](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) 并单击 **[!UICONTROL +添加新]** 功能以 [添加新集成](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在 **[!UICONTROL 显示]** 列表中，选择 **[!UICONTROL 按名称]** ，然后将 [!DNL ~合作伙伴~] 集成拖动到空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 接收此集成中的数据的报表包。 |
| 集成名称 | 指定数据连接器显示在报表包的活动集成列表中的集成名称。 |
| 帐户ID | 指定Aprimo帐户ID。 |
| Recipient ID | 此ID是Aprimo系统中电子邮件地址的编码或数字表示形式。此“收件人ID”与网站收件人ID上的下游访客行为(购物车放弃、购买等)相关联。它被引入Aprimo系统，并可利用它进行再营销。 |
| Clicked | (必需)指定用于存储从电子邮件系统中导入的电子邮件单击数据的Adobe Analytics事件。单击“单击”事件可查看单击该电子邮件的访客的数量。 |
| 消息ID | (必需)存储唯一邮寄ID。 |
| 已打开 | (必需)指定用于存储通过电子邮件系统导入的电子邮件打开数据的Adobe Analytics事件。打开的活动可让您查看打开电子邮件的访客的数量。 |
| Recipient ID | (必需)存储唯一访客ID。 |
| 已发送 | (必需)指定用于存储通过电子邮件系统导入的电子邮件的Adobe Analytics事件。通过“发送的活动”，可以查看发送的电子邮件的数量。 |
| 跳出次数 | (必需)指定Adobe Analytics事件，该事件存储从电子邮件系统导入的电子邮件总退回数据。“总退回次数”事件可让您查看由于交付问题而未发送给收件人的电子邮件数。 |
| 取消订阅 | (必需)指定用于存储从电子邮件系统中导入的电子邮件取消订阅数据的Adobe Analytics事件。通过取消订阅活动，您可以查看打开电子邮件的访客数量，但单击取消订阅链接以退出单位以后的电子邮件消息。 |
| 区段 | 此集成可创建合作伙伴定义区段中显示的合作伙伴定义区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用推荐的访问权限。 |
| 数据收集 | 如果 **要使用** s_ code. js插件作为此集成的集合模型，请选择JavaScript插件。 |
如果您要将自动收集模型用于此集成，请选择 **“自动解决方案** ”，然后指定用于此集成的唯一标识符。如果选择此选项，则指定用于此集成的唯一标识符：
<ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加给登陆页面URL的消息ID。</li>
<li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴的登录页面URL的收件人ID附加。</li></ul>||
|控制面板和书签生成|自动生成集成的仪表板和书签。|
