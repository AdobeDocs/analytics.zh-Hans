---
title: account
description: 使用 account 变量确定要将数据发送到的报表包。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 47%

---

# account

>[!IMPORTANT]
>
>此变量已停用。如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* 如果您使用Web SDK，则报表包位于Web SDK将数据发送到的数据流中的Adobe Analytics服务设置中。
* 如果您使用Adobe Analytics扩展，则报表包位于 [!UICONTROL 库管理] 配置Adobe Analytics扩展时的折叠面板。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函数来实例化Analytics跟踪对象，报表包ID已作为函数中的必需参数存在。
