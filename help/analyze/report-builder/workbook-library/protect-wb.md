---
description: 您可以锁定工作簿，从而防止对工作簿中的所有请求执行添加和编辑操作。这允许通过暂停所有报表请求来脱机编辑工作簿，从而提高编辑效率。
seo-description: 您可以锁定工作簿，从而防止对工作簿中的所有请求执行添加和编辑操作。这允许通过暂停所有报表请求来脱机编辑工作簿，从而提高编辑效率。
seo-title: 锁定/解锁工作簿
solution: Analytics
title: 锁定/解锁工作簿
topic: Report Builder
uuid: ef5c276c-5f74-4741-b6 fa-4c79 edia29 f62
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 锁定/解锁工作簿

您可以锁定工作簿，从而防止对工作簿中的所有请求执行添加和编辑操作。这允许通过暂停所有报表请求来脱机编辑工作簿，从而提高编辑效率。

作为分析人员，锁定工作簿可以保护工作簿请求不被组织内的其他用户篡改。与此同时，这些用户仍可以刷新工作簿中的请求。

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

）的发行信息。

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

）的发行信息。

如果您具有以下权限之一，则可以解锁已锁定的工作簿：

* 您是管理员，或者
* 您是最初锁定工作簿的人员。在这种情况下，您不必是管理员。

>[!NOTE]
>
>除非拥有解锁工作簿的权限，否则不能向受保护的工作簿添加请求。

当锁定工作簿以防止编辑请求时，

* 用户无法创建/添加请求。
* 用户无法通过“请求向导”编辑请求。
* 用户无法通过“编辑多个请求”功能编辑请求。
* 用户无法剪切、复制或粘贴请求。但是，用户仍可以使用本机 Excel 的“剪切”/“复制”/“粘贴”上下文菜单来剪切/复制/粘贴请求的内容。
* 用户可以单独或作为群组的一部分刷新请求。
* 如果请求使用来自单元格（日期范围、区段、过滤器）的输入值，则用户可以在单元格中更改这些值，从而通过刷新请求间接对其进行编辑。

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* 如果您不具有解锁请求的权限，则会出现以下提示：

   ![](assets/locked_workbook_error.png)

* 如果您具有所需的权限，则不会出现任何提示，您可以顺利编辑请求。

## 工作流程 {#section_260D05FF632B41DB97DB43E2ADBE2E75}

我们假定工作簿 A 具有一个请求，该工作簿处于锁定状态，且由用户 A 创建。

**示例1：管理员用户(或用户A)**

1. 用户登录到 Report Builder 并打开工作簿 
1. 工作簿 A 当前已锁定，因此“创建请求”按钮在工具栏中处于停用状态，且所有其他按钮的功能均因锁定而被禁用。
1. 如果用户尝试使用任一停用的按钮，则会出现一条消息，说明该工作簿当前已锁定。
1. 用户可以解锁该工作簿，从而启用完全编辑功能。
1. 解锁后，该工作簿会保持解锁状态，直至重新明确地将其锁定。

**示例2：非管理员用户(用户B)**

1. 用户登录到 Report Builder 并打开工作簿 
1. 用户无法添加/编辑请求。
1. 用户无法解锁工作簿。

