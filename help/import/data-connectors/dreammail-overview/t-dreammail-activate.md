---
description: 使用 Adobe Data Connectors 配置向导来设置集成。
title: 激活集成
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
exl-id: b0d6849b-975a-4476-a2d3-36abeee12273
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 96%

---

# 激活集成{#activate-the-integration}

使用 Adobe Data Connectors 配置向导来设置集成。

1. 启动 [Data Connectors](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html)，然后单击 **[!UICONTROL + 新增]**&#x200B;以[添加新集成](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html)。
1. 在&#x200B;**[!UICONTROL 显示]**&#x200B;列表中，选择&#x200B;**[!UICONTROL 按名称]**，然后将 [!DNL ~Partner~] 集成拖至空插件插槽。
1. 使用下表中的信息完成集成向导：

| 字段 | 描述 |
|--- |--- |
| 报表包 | 从此集成接收数据的报表包。 |
| 集成名称 | 指定 Data Connectors 在报表包的活动集成列表中显示的集成名称。 |
| 集成 UUID | 指定您的 DreamMail 集成 UUID。 |
| 客户端名称 | 指定您的 DreamMail 客户端名称。 |
| 网站名称 | 指定您的 DreamMail 网站名称。 |
| 退回 | 由于传输问题而未发送给收件人的电子邮件数量。 |
| 已送达 | 消息发送成功的次数。 |
| 发送错误 | 消息发送失败的次数。 |
| HTML 打开 | 打开了电子邮件的访客数量。 |
| 无效 | 无效的电子邮件地址数量。 |
| 促销活动 | 市场促销活动 ID。 |
| 传递次数 | “已点击”事件让您能够查看点击了电子邮件的访客数量。 |
| 电子邮件 eVar | DreamMail 系统中的电子邮件地址。此“电子邮件 eVar”与提取到 DreamMail 系统中的网站下游访客行为（放弃购买、购买等）相关联，且可用于再营销。 |
| 焦点事件 | 可在再营销区段中导出的事件。 |
| 焦点购买 | 可在再营销区段中导出的事件。 |
| 焦点值 | 可在再营销区段中导出的收入事件。 |
| 总点击量 | “已点击”事件让您能够查看点击了电子邮件的访客数量。 |
| 区段 | 此集成会创建在“合作伙伴区段”部分中显示的合作伙伴定义的区段。此外，您还可以选择要包含在集成中的现有报表包级别区段。 |
| 访问请求 | 启用建议的访问权限。 |
| 数据收集 | 如果要使用 s_code.js 插件作为此集成的收集模型，请选择 **JavaScript 插件**（请参阅 ）。如果要为此集成使用自动收集模型，请选择&#x200B;**自动解决方案**，然后指定用于此集成的唯一标识符。如果选择此选项，请指定用于此集成的唯一标识符：<ul><li>消息 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的消息 ID。</li><li>收件人 ID 查询字符串参数：此值表示电子邮件合作伙伴附加到登陆页面 URL 的收件人 ID。</li></ul> |
| 功能板和书签生成 | 自动为集成生成功能板和书签。 |
