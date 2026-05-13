---
title: account
description: （已停用）确定要将数据发送到的报表包。
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: https://experienceleague.adobe.com/TmNxbAFJXxEnMJZNNZKP1ldkmeYICEzKdNoptNChzko
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>此变量已停用。 如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。 需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* 如果您使用Web SDK，则报表包位于Web SDK将数据发送到的数据流中的Adobe Analytics服务设置中。
* 如果使用Adobe Analytics扩展，则在配置Adobe Analytics扩展时，报表包位于[!UICONTROL 库管理]折叠面板中。
* 如果使用[`s_gi()`](../functions/s-gi.md)函数实例化Analytics跟踪对象，则报表包ID已作为该函数中的必需参数而存在。
