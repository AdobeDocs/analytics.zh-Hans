---
description: Data Warehouse提供了一项允许您提取访客ID列表的功能。 这些ID不是Cookie ID，而是您在一个转化变量中捕获的ID。 尽管可通过其他方法获取此信息，但以下示例是生成Data Warehouse请求的快捷方式。
title: 用例 — 提取访客 ID
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: 'https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 10%

---

# 用例 — 提取访客 ID

Data Warehouse提供了一项允许您提取访客ID列表的功能。 这些ID不是Cookie ID，而是您在一个转化变量中捕获的ID。 尽管可通过其他方法获取此信息，但以下示例是生成Data Warehouse请求的快捷方式。

例如，假设您的企业向客户和潜在客户发送营销电子邮件。 则每个电子邮件收件人在您的电子邮件系统中均有一个唯一的 ID（如 *`EMAIL Contact ID`*）。 您可以设置电子邮件，以便当联系人收到电子邮件并单击其链接之一时，访客可以使用促销活动ID和唯一的电子邮件联系人ID访问您的网站。 例如，您的电子邮件链接可能会解析为：

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

通过在转化变量(eVar)中设置这些变量，您可以查看每个电子邮件的执行情况（通过促销活动ID）以及每个电子邮件收件人访问网站的频率（通过电子邮件联系人ID）。

假设您正在捕获这些ID。 大多数营销人员希望对其网站行为进行分段，然后查看是否可以向符合特定标准的访客进行再营销。 例如，您可能希望向通过电子邮件访问您的网站并查看（或完成）网站表单的所有电子邮件收件人发送再营销电子邮件。 为此，请找到一种方法来识别完成特定表单的人员的EMAIL Contact ID。

这样做的一种方式是使用转化子关系报表，按电子邮件联系人ID eVar划分表单ID eVar值。 但是，预先构建的功能可以通过Data Warehouse来实现这一点。 通过此功能，您可以了解哪个eVar存储了您的独特用户ID（在此例中是电子邮件联系人ID），并可以使用Data Warehouse轻松提取这些ID。 通过使用此功能，您可以自动创建一个Data Warehouse请求，以提取您感兴趣的唯一访客ID。
