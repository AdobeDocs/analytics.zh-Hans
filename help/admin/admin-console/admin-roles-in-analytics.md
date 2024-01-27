---
title: Adobe Analytics 中的管理员角色
description: 了解如何开始使用 Adobe Analytics、常规角色类型以及如何登录到 UI。
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 100%

---

# Adobe Analytics 中的管理员角色

Adobe Analytics 支持各种类型的管理员。具有完全访问权限的 Adobe Analytics 管理员可以访问 Adobe Analytics 中的所有内容，而其他管理员和用户可以执行更专业性的任务。

>[!NOTE]
>
>必须先在 Experience Cloud 中将任一用户分配为第一个管理员，之后才能在 Adobe Analytics 中为该用户分配角色。随后，第一个管理员可以为组织中的用户设置其他重要角色，如本文所述。有关第一个管理员的更多信息，请参阅 [Adobe Analytics 管理入门指南](/help/admin/admin-console/first-admin-guide.md)。


## Experience Cloud 和 Adobe Analytics 中的重要角色

在使用 Adobe Analytics 时，请考虑以下重要角色：

* **拥有完全访问权限的 Adobe Analytics 管理员**：此类用户拥有对 Adobe Analytics 中所有功能的完全访问权限，包括报表包设置和用户权限。 根据贵组织的组成结构，可由不同的人员或团队分别负责 Analytics 管理所涉及的各方面工作。例如，一个人负责指定实施中使用的变量。而另一个人负责确保每个用户均具有正确权限，从而能够正常获取所需报表。至少确定一位负责 Analytics 报表包设置和用户权限的用户，该用户可以邀请其他 Analytics 管理员。
* **数据收集管理员：**&#x200B;此类用户拥有对 Adobe Experience Platform 数据收集中所有功能的完全访问权限，包括发布权限、创建容器和访问用户权限。此类用户不一定得是程序员，但若能掌握 HTML、CSS 和 JavaScript 的入门级或更高级别的知识，将有助于他们开展工作。为在您的网站上实施标记，此类用户需要与您组织的网站所有者合作。请至少确定一位负责您组织实施的用户，这些用户可以邀请其他数据收集管理员。
* **产品配置文件管理员：**&#x200B;此类用户可以在产品配置文件中添加或移除用户，调整其产品配置文件中的权限项，以及将产品配置文件分配给用户组或从用户组中删除产品配置文件。 产品配置文件管理员没有 Adobe Analytics 的完全访问权限。 不过，如果团队领导或经理需要为团队授予并管理 Adobe Analytics 的访问权限，那么产品配置文件管理员将是他们的不二之选。有关产品配置文件的更多信息，请参阅 [Adobe Analytics 的产品配置文件](/help/admin/admin-console/permissions/product-profile.md)。
* **支持代表**：也称为受支持用户，他们在 Analytics 界面中没有其他权限。他们而是会在与 Adobe 客户关怀团队通信时获得其他权限。这些用户几乎都是 Analytics 管理员，这有助于客户关怀团队对这些用户的问题进行故障诊断。请至少确定一位 Analytics 管理员，负责促进最终用户与 Adobe 客户关怀团队之间的交互。
* **网站所有者：**&#x200B;网站所有者可以是个人或团队，负责网站的编码和开发工作。他们不需要具有帐户，但需要与数据收集管理员合作，以获取标记代码并在您的网站上实施该代码。
* **最终用户**：最终用户一般负责查看报表并寻找业务问题的答案。Analytics 管理员会向最终用户授予产品使用权限。

## 授予 Analytics 产品管理员完全访问权限

系统级别管理员无法直接访问产品；但他们可以通过将自己添加为产品级管理员来为自己授予产品访问权限。

为您自己或他人授予 Adobe Analytics 访问权限：

1. 使用您的 Adobe ID 凭据登录到 [Admin Console](https://adminconsole.adobe.com/)。
1. 单击顶部的&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡。贵组织购买的所有产品都位于左侧。单击 **[!UICONTROL Adobe Analytics]**，然后单击&#x200B;**[!UICONTROL 新建配置文件]**&#x200B;按钮。
1. 将此配置文件命名为“Analytics 完全管理员访问权限”，然后单击&#x200B;**[!UICONTROL 下一步]**>**[!UICONTROL 保存]**。
1. 返回至产品配置文件页面，单击新建的配置文件，然后单击&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。
1. 单击任一权限行项。如果&#x200B;**[!UICONTROL 自动包含]**&#x200B;可用，请启用该项。如果&#x200B;**[!UICONTROL 自动包含]**&#x200B;不可用，请单击&#x200B;**[!UICONTROL 全部添加]**。这两个选项都会将权限项移到右列。
1. 单击&#x200B;**[!UICONTROL 保存]**。对所有权限类别重复上述步骤。
1. 为配置文件授予所有类别的权限后，单击顶部的&#x200B;**[!UICONTROL 产品]**&#x200B;以返回至“产品”页面。
1. 在 Adobe Analytics 拼贴下，单击&#x200B;**[!UICONTROL 指定用户]**。
1. 输入要向其授予 Analytics 完全访问权限的电子邮件地址，并为其分配新创建的具有完全管理员访问权限的配置文件。单击&#x200B;**[!UICONTROL 保存]**。

此时，用户将拥有对 Adobe Analytics 的完全访问权限。

## 授予产品管理员对 Experience Platform 中数据收集的访问权限

授予产品管理员对 Experience Platform 中数据收集的访问权限与授予产品管理员对 Analytics 的访问权限几乎一模一样。

1. 使用您的 Adobe ID 凭据登录 [Adobe Admin Console](https://adminconsole.adobe.com)。
1. 单击顶部的&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡。贵组织购买的所有产品都位于左侧。单击 **[!UICONTROL Experience Platform Launch]**，然后单击&#x200B;**[!UICONTROL 新配置文件]**。
1. 将此配置文件命名为“数据收集完全管理员访问权限”，然后单击&#x200B;**[!UICONTROL 完成]**。
1. 返回至&#x200B;**[!UICONTROL 产品配置文件]**&#x200B;页面，单击新建的配置文件，然后单击&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。
1. 单击任一权限行项。如果&#x200B;**[!UICONTROL 自动包含]**&#x200B;可用，请启用该项。如果“自动包含”不可用，请单击&#x200B;**[!UICONTROL 全部添加]**。这两个选项都会将权限项移到右列。
1. 单击&#x200B;**[!UICONTROL 保存]**。对所有权限类别重复上述步骤。
1. 为配置文件授予所有类别的权限后，单击顶部的&#x200B;**[!UICONTROL 概述]**，以返回至“概述”页面。
1. 在 [!UICONTROL Experience Platform Launch] 图块下，单击&#x200B;**[!UICONTROL 指定用户]**。
1. 输入要向其授予 Analytics 完全访问权限的电子邮件地址，并为其分配新创建的具有完全管理员访问权限的配置文件。单击&#x200B;**[!UICONTROL 保存]**。
1. 此时，用户将拥有对 Experience Platform 数据收集的完全访问权限。

## 授予产品配置文件的完全产品管理员访问权限

有关将用户分配为产品配置文件管理员的信息，请参阅《企业用户指南》的[管理企业用户的产品配置文件](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)一文中的“管理产品配置文件管理员”部分。

## 后续步骤

[创建报表包](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：让您的 Analytics 管理员登录到该工具，并创建用于收集数据的报表包

[创建 Analytics 标记属性](/help/implement/launch/create-analytics-property.md)：让您的数据收集管理员登录该工具，并创建一个要在您的网站上实施的属性

必须先在 Experience Cloud 中将任一用户分配为第一个管理员，之后才能在 Adobe Analytics 中为该用户分配角色。随后，第一个管理员可以为组织中的用户设置其他重要角色，如本文所述。

为使组织内其他成员能够使用各个 Experience Cloud 解决方案，首先需确定一个管理员，即第一个管理员。

签署合同后

1. Adobe 设置团队将着手准备创建帐户。

1. 在合同正式生效之前，第一个管理员会收到一封包含登录凭据的电子邮件。

>[!IMPORTANT]
>
>   强烈建议先向 Adobe 提供第一个管理员的联系信息，并在确认信息正确无误后再签署合同。
