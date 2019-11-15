---
description: 设置希望条件要触发的操作。
keywords: Dynamic Tag Management;rule;create rule;new rule;javascript/third party tags;set up actions for condition;add new script;non-sequential javascript;sequential javascript;non-sequential html
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 设置条件要触发的操作
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 设置条件要触发的操作

设置希望条件要触发的操作。

在设置条件之后，您必须设置希望该条件触发的操作。这些操作包括 [!DNL Analytics] 事件、第三方标记和自定义脚本。以下示例描述如何设置脚本或第三方标记。

除了 [!DNL Adobe Analytics] 和 Google Analytics 之类的集成工具以外，动态标签管理还可以触发任何类型的 JavaScript 或将 HTML 注入您网站中的选定页面或特定方案。

每个规则都可以触发任意所需数量的脚本或 HTML 注入。

> [!NOTE] 由于DTM允许您将自定义代码插入页面，请注意不要创建跨站点脚本(XSS)漏洞(有关详细信息，请参阅 [OWASP的指南](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) )。 在脚本中使用数据元素时需要特别注意。应始终假定数据元素值来自不受信任的源。

**设置条件要触发的操作**

1. 单击 **[!UICONTROL JavaScript/第三方标记]**，以向您的规则中添加新脚本。

   ![](assets/scripts-actions.png)

1. 单击&#x200B;**[!UICONTROL 添加新脚本]**。

   ![](assets/scripts-actions2.png)

1. 命名脚本。
1. 指定您希望脚本如何触发，并将所需的内容粘贴到文本区域中。![](assets/scripts-actions3.png)

1. 单击&#x200B;**[!UICONTROL 保存代码]**，脚本随即将会添加到规则的队列中。![](assets/scripts-actions4.png)

