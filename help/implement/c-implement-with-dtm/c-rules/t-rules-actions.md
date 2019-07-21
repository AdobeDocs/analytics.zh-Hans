---
description: 设置希望条件要触发的操作。
keywords: 动态标签管理；规则；创建规则；新规则；javascript/第三方标记；设置条件的操作；添加新脚本；非顺序javascript；orderal javascript；非顺序html
seo-description: 设置希望条件要触发的操作。
seo-title: 设置条件要触发的操作
solution: Marketing Cloud、Analytics、Target、动态标签管理
title: 设置条件要触发的操作
uuid: 2e892f0b-7261-41ee-b849-6e3054 a38 de0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 设置条件要触发的操作

设置希望条件要触发的操作。

在设置条件之后，您必须设置希望该条件触发的操作。这些操作包括 [!DNL Analytics] 事件、第三方标记和自定义脚本。以下示例描述如何设置脚本或第三方标记。

除了 [!DNL Adobe Analytics] 和 Google Analytics 之类的集成工具以外，动态标签管理还可以触发任何类型的 JavaScript 或将 HTML 注入您网站中的选定页面或特定方案。

每个规则都可以触发任意所需数量的脚本或 HTML 注入。

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). 在脚本中使用数据元素时需要特别注意。应始终假定数据元素值来自不受信任的源。

**设置条件要触发的操作**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Click **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. 命名脚本。
1. Specify how you want the script to trigger, and paste the desired content into the text area. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

