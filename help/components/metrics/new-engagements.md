---
title: 新参与
description: 设置首次接触渠道的次数。
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# 新参与

“新参与”量度[量度](overview.md)显示访客在该访客的参与期内首次匹配营销渠道的次数。 当您希望将任何维度与首次匹配营销渠道处理规则的访客进行比较时，此量度非常有用。

## 如何计算此指标

在数据处理过程中，每次点击都会通过[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)。 如果点击与任何营销渠道处理规则匹配，且访客尚无首次接触渠道，则该点击是新参与。 如果点击与任何营销渠道处理规则不匹配，或者如果访客已经拥有首次接触渠道，则该点击不是新参与。

如果访客的参与期限到期，则他们可能会有多个新的参与。
