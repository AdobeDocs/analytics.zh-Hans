---
title: 新参与
description: 设置首次接触渠道的次数。
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# 新参与

“新参与”量度[量度](overview.md)显示访客在该访客的参与期内首次匹配营销渠道的次数。 当您希望将任何维度与首次匹配营销渠道处理规则的访客进行比较时，此量度非常有用。

## 如何计算此量度

在数据处理过程中，每次点击都会通过[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)。如果点击与任何营销渠道处理规则匹配，且访客尚无首次接触渠道，则该点击是新参与。如果点击与任何营销渠道处理规则不匹配，或者如果访客已经拥有首次接触渠道，则该点击不是新参与。

如果访客的参与期限到期，则他们可能会有多个新的参与。
