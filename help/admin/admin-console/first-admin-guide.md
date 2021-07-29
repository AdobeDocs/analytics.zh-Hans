---
title: Adobe Analytics 管理入门指南
description: 了解如何开始使用 Adobe Analytics、常规角色类型以及如何登录到用户界面。
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 72%

---

# Adobe Analytics 管理入门指南

为使组织内其他成员能够使用各个 Experience Cloud 解决方案，首先需确定一个管理员，即第一个管理员。与 Adobe 签署合同后，Adobe 配备团队将着手准备创建帐户。在合同正式生效之前，第一个管理员会收到一封包含登录凭据的电子邮件。强烈建议先向 Adobe 提供第一个管理员的联系信息，并在确认信息正确无误后再签署合同。

## 使用 Experience Cloud 时涉及的若干重要角色

如果贵组织已购买 Adobe Analytics，应考虑以下几个重要角色：

* **Adobe Analytics 管理员**：此类用户拥有对 Adobe Analytics 中所有功能的完全访问权限，包括报表包设置和用户权限。根据贵组织的组成结构，可由不同的人员或团队分别负责 Analytics 管理所涉及的各方面工作。例如，一个人负责指定实施中使用的变量。而另一个人负责确保每个用户均具有正确权限，从而能够正常获取所需报表。至少确定一位负责 Analytics 报表包设置和用户权限的用户，该用户可以邀请其他 Analytics 管理员。
* **数据收集管理员：** 这些用户对数据收集UI(以前称为Experience Platform LaunchUI)中的所有内容具有完全访问权限，包括发布权限、创建容器和用户权限。此类用户不一定得是程序员，但若能掌握 HTML、CSS 和 JavaScript 的入门级或更高级别的知识，将有助于他们开展工作。他们负责与贵组织的网站所有者合作，以在您的网站上实施Experience Platform标记。 请至少确定一位负责贵组织实施的用户，该用户可以邀请其他数据收集管理员。
* **支持代表**：也称为受支持用户，他们在 Analytics 界面中没有其他权限。他们而是会在与 Adobe 客户关怀团队通信时获得其他权限。这些用户几乎都是 Analytics 管理员，这有助于客户关怀团队对这些用户的问题进行故障诊断。请至少确定一位 Analytics 管理员，负责促进最终用户与 Adobe 客户关怀团队之间的交互。
* **网站所有者**：网站所有者可以是个人或团队，负责网站的编码和开发工作。他们不需要帐户，但需要与数据收集管理员合作以获取标记代码并在您的网站上实施该代码。
* **最终用户**：最终用户一般负责查看报表并寻找业务问题的答案。Analytics 管理员会向最终用户授予产品使用权限。

作为第一个管理员，您的角色可能会与上述一个或多个角色重叠。只要您的职权范围涵盖了上述所有基本职责，您便可以向组织内的其他人员授予相应权限，以便其他人可以开始工作。

## 授予 Analytics 的产品管理员访问权限

系统级别管理员无法直接访问产品，但他们可以通过将自己添加为产品级管理员来为自己授予产品访问权限。如果您希望向自己或其他人授予 Adobe Analytics 的访问权限，可以执行以下步骤。

1. 使用您的 Adobe ID 凭据登录到 [Admin Console](https://adminconsole.adobe.com/)。
1. 单击顶部的“产品”选项卡。贵组织购买的所有产品都位于左侧。单击“Adobe Analytics”，然后单击“新建配置文件”按钮。
1. 将此配置文件命名为“Analytics 完全管理员访问权限”，然后单击“完成”。
1. 返回至“产品配置文件”页面，单击新建的配置文件，然后单击“权限”选项卡。
1. 单击任一权限行项。如果“自动包含”可用，请启用该项。如果“自动包含”不可用，请单击“全部添加”项。这两个选项都会将权限项移到右列。
1. 单击“保存”。对所有权限类别重复上述步骤。
1. 为配置文件授予所有类别的权限后，单击顶部的“概述”，以返回至“概述”页面。
1. 在“Adobe Analytics”图标下，单击“指定用户”。
1. 输入要向其授予 Analytics 完全访问权限的电子邮件地址，并为其分配新创建的具有完全管理员访问权限的配置文件。单击“保存”。
1. 此时，用户将拥有对 Adobe Analytics 的完全访问权限。

## 授予产品管理员在中收集数据的访问权限Experience Platform

在Experience Platform中为数据收集授予产品管理员访问权限几乎与为Analytics授予产品管理员访问权限几乎相同。

1. 使用您的Adobe ID凭据登录到[Adobe Admin Console](https://adminconsole.adobe.com)。
1. 单击顶部的&#x200B;**[!UICONTROL Products]**&#x200B;选项卡。 贵组织购买的所有产品都位于左侧。单击&#x200B;**[!UICONTROL Experience Platform Launch]**，然后单击&#x200B;**[!UICONTROL 新建配置文件]**。
1. 将此配置文件命名为“数据收集完全管理员访问”，然后单击&#x200B;**[!UICONTROL Done]**。
1. 返回至&#x200B;**[!UICONTROL 产品配置文件]**&#x200B;页面，单击新创建的配置文件，然后单击&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。
1. 单击任一权限行项。如果&#x200B;**[!UICONTROL 自动包含]**&#x200B;可用，请启用它。 如果“自动包含”不可用，请单击&#x200B;**[!UICONTROL Add all]**。 这两个选项都会将权限项移到右列。
1. 单击&#x200B;**[!UICONTROL 保存]**。对所有权限类别重复上述步骤。
1. 向配置文件授予所有权限类别后，单击顶部的&#x200B;**[!UICONTROL Overview]**，返回至“概述”页面。
1. 在[!UICONTROL Experience Platform Launch]拼贴下，单击&#x200B;**[!UICONTROL 分配用户]**。
1. 输入要向其授予 Analytics 完全访问权限的电子邮件地址，并为其分配新创建的具有完全管理员访问权限的配置文件。单击&#x200B;**[!UICONTROL 保存]**。
1. 用户现在拥有Experience Platform数据收集的完全访问权限。

## 后续步骤

[创建报表包](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：让您的 Analytics 管理员登录到该工具，并创建用于收集数据的报表包

[创建Analytics标记属性](/help/implement/launch/create-analytics-property.md):让您的数据收集管理员登录到该工具，并创建要在您的网站上实施的资产
