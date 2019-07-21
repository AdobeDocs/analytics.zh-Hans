---
description: Data Warehouse 提供了一项可提取访客 ID 列表的功能。这些 ID 不是 Cookie ID，而是在您的任一转化变量中捕获的 ID。尽管有其他方法可获取此信息，但是以下示例提供了一种可快速生成 Data Warehouse 请求的方法。
seo-description: Data Warehouse 提供了一项可提取访客 ID 列表的功能。这些 ID 不是 Cookie ID，而是在您的任一转化变量中捕获的 ID。尽管有其他方法可获取此信息，但是以下示例提供了一种可快速生成 Data Warehouse 请求的方法。
seo-title: 使用案例 - 提取访客 ID
solution: Analytics
title: 使用案例 - 提取访客 ID
topic: 管理工具
uuid: ed228334-619c-43d7-b781-a18 af73 b00 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用案例 - 提取访客 ID

Data Warehouse 提供了一项可提取访客 ID 列表的功能。这些 ID 不是 Cookie ID，而是在您的任一转化变量中捕获的 ID。尽管有其他方法可获取此信息，但是以下示例提供了一种可快速生成 Data Warehouse 请求的方法。

例如，假设您的企业向客户和潜在客户发送营销电子邮件。则每个电子邮件收件人在您的电子邮件系统中均有一个唯一的 ID（如 *`EMAIL Contact ID`*). 您可以设置您的电子邮件，以便联系人在收到电子邮件并单击其中的某个链接时，到达您网站的访客会具有一个促销活动 ID 和唯一电子邮件联系人 ID。例如，您的电子邮件链接可能解析为：

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

在转化变量 (eVar) 中对此进行设置，以便您可以了解每个电子邮件的效果如何（通过促销活动 ID）以及每个电子邮件收件人访问网站的频率（通过电子邮件联系人 ID）。

假设您要捕获这些 ID。大多数营销商希望对这些网站行为进行细分，以了解是否可对满足特定条件的收件人进行再营销。例如，您可能想要向通过电子邮件访问您网站并查看（或完成）了网站表单的所有电子邮件收件人发送再营销信息。为此，您需要找到一种方法，识别完成了特定表单的收件人的电子邮件联系人 ID。

方法之一是使用转化子关系报表按电子邮件联系人 ID eVar 划分表单 ID eVar 值。但是，有一种预置功能也可使用 Data Warehouse 来达到这一目的。此功能可以指定由哪个 eVar 存储您的唯一用户 ID（此案例中的电子邮件联系人 ID），使您可使用 Data Warehouse 轻松提取这些 ID。通过使用此功能，可自动创建数据仓库请求，提取您感兴趣的独特访客 ID。
