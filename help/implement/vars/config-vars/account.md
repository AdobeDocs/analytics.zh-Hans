---
title: account
description: 使用帐户变量确定将数据发送到的报表包。
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# account

> [!IMPORTANT] 此变量已停用。 如果您 [`s.sa()`](../functions/sa-method.md) 的实施需要修改报表包目标，请使用该函数。

在Adobe Analytics的先前版本中，变 `account` 量决定了要将数据发送到的报表包。 向Adobe Analytics发送数据需要报表包ID。

* 如果您使用Adobe Experience Platform Launch，则在配置Adobe Analytics扩展时，报表包位于“ [!UICONTROL 库管理] ”折叠式面板下。
* 如果使用函 `s_gi()` 数实例化Analytics跟踪对象，则报表包ID已作为函数中的必需参数存在。
