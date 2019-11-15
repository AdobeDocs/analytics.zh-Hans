---
description: 使用Adobe Data Connectors配置向导设置集成。
title: 激活集成
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 激活集成 {#activate-the-integration}

使用Adobe Data Connectors配置向导设置集成。

1. 启动 [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) ，然后单击 **[!UICONTROL +添加新]** , [以添加新集成](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在“显 **[!UICONTROL 示]** ”列表中，选择“按名 **[!UICONTROL 称]** ”，然后将 [!DNL ~Partner~] integration拖至空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 从此集成接收数据的报表包。 |
| 集成名称 | 指定数据连接器在报表包的“活动集成列表”中显示的集成名称。 |
| 帐户ID | 指定您的Aprimo帐户ID。 |
| Recipient ID | 此ID是Aprimo系统中电子邮件地址的编码或数字表示形式。 此“收件人ID”与网站收件人ID（购物车放弃、购买等）上的下游访客行为相关联它被引入Aprimo系统，并可用于再营销目的。 |
| 已单击 | （必需）指定Adobe Analytics事件，用于存储从电子邮件系统导入的电子邮件已点击数据。 通过“已点击”事件，您可以查看点击电子邮件的访客数。 |
| 消息ID | （必需）存储唯一的邮寄ID。 |
| 已打开 | （必需）指定Adobe Analytics事件，用于存储从电子邮件系统导入的电子邮件已打开数据。 通过“已打开”活动，您可以查看打开电子邮件的访客数。 |
| Recipient ID | （必需）存储唯一访客ID。 |
| 已发送 | （必需）指定Adobe Analytics事件，用于存储从电子邮件系统导入的电子邮件已发送数据。 通过“已发送”活动，您可以查看已发送的电子邮件数。 |
| 跳出次数 | （必需）指定存储从电子邮件系统导入的电子邮件总弹回次数数据的Adobe Analytics事件。 “总弹回次数”事件可让您查看由于传送问题而未发送给收件人的电子邮件数。 |
| 取消订阅 | （必需）指定存储从电子邮件系统导入的电子邮件取消订阅数据的Adobe Analytics事件。 通过取消订阅活动，您可以查看打开电子邮件但随后单击取消订阅链接以选择退出您组织的将来电子邮件的访客数量。 |
| 区段 | 此集成创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。 此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果 **** 要使用s_code.js插件作为此集成的集合模型，请选择“JavaScript插件”。 |
如果 **要为此集成使用自动收集模型** ，请选择自动化解决方案，然后指定用于此集成的唯一标识符。 如果选择此选项，请指定用于此集成的唯一标识符：
<ul><li>消息ID查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面URL的消息ID。</li>
<li>收件人ID查询字符串参数：此值表示电子邮件合作伙伴附加到登录页面URL的收件人ID。</li></ul>||功能板和书签生成|自动生成功能板和书签以进行集成。|
