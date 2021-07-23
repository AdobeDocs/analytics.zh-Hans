---
title: account
description: 使用 account 变量确定要将数据发送到的报表包。
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 80%

---

# 帐户

>[!IMPORTANT]
>
>此变量已停用。如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* 如果在Adobe Experience Platform中使用标记，则在配置Adobe Analytics扩展时，报表包位于[!UICONTROL 库管理]折叠面板下。
* 如果使用 [`s_gi()`](../functions/s-gi.md) 函数实例化 Analytics 跟踪对象，则报表包 ID 已作为该函数中的必需参数而存在。
