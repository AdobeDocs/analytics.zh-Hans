---
title: account
description: 使用 account 变量确定要将数据发送到的报表包。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# account

>[!IMPORTANT] 此变量已停用。如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* If you use Adobe Experience Platform Launch, report suites reside under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.
* 如果使用 [`s_gi()`](../functions/s-gi.md) 函数实例化 Analytics 跟踪对象，则报表包 ID 已作为该函数中的必需参数而存在。
