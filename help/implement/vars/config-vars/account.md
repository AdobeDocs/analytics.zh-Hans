---
title: account
description: 使用 account 变量确定要将数据发送到的报表包。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 47%

---

# 帐户

>[!IMPORTANT]
>
>此变量已停用。如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* 如果您使用Web SDK，则报表包位于Web SDK将数据发送到的数据流中的Adobe Analytics服务设置中。
* 如果您使用Adobe Analytics扩展，则报表包位于 [!UICONTROL 库管理] 折叠面板。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函数实例化Analytics跟踪对象时，报表包ID已作为函数中的必需参数存在。
