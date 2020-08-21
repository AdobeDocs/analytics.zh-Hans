---
title: account
description: 使用 account 变量确定要将数据发送到的报表包。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---


# account

>[!IMPORTANT]
>
>此变量已停用。如果您的实施需要修改报表包目标，请使用 [`s.sa()`](../functions/sa-method.md) 函数。

在早期版本的 Adobe Analytics 中，`account` 变量用于确定要将数据发送到的报表包。需要具有报表包 ID 才能将数据发送到 Adobe Analytics。

* 如果使用 Adobe Experience Platform Launch，则在配置 Adobe Analytics 扩展时，报表包位于[!UICONTROL 库管理]折叠面板中。
* 如果使用 [`s_gi()`](../functions/s-gi.md) 函数实例化 Analytics 跟踪对象，则报表包 ID 已作为该函数中的必需参数而存在。
