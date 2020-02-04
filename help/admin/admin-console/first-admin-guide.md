---
title: Adobe Analytics 管理入门指南
description: 了解如何开始使用 Adobe Analytics、常规角色类型以及如何登录到用户界面。
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Adobe Analytics 管理入门指南

为使组织内其他成员能够使用各个 Experience Cloud 解决方案，首先需确定一个管理员，即第一个管理员。与 Adobe 签署合同后，Adobe 配备团队将着手准备创建帐户。在合同正式生效之前，第一个管理员会收到一封包含登录凭据的电子邮件。强烈建议先向 Adobe 提供第一个管理员的联系信息，并在确认信息正确无误后再签署合同。

## 使用 Experience Cloud 时涉及的若干重要角色

如果贵组织已购买 Adobe Analytics，应考虑以下几个重要角色：

- **Adobe Analytics 管理员**：此类用户拥有对 Adobe Analytics 中所有功能的完全访问权限，包括报表包设置和用户权限。根据贵组织的组成结构，可由不同的人员或团队分别负责 Analytics 管理所涉及的各方面工作。例如，一个人负责指定实施中使用的变量。而另一个人负责确保每个用户均具有正确权限，从而能够正常获取所需报表。至少确定一位负责 Analytics 报表包设置和用户权限的用户，该用户可以邀请其他 Analytics 管理员。
- **Adobe Experience Platform Launch 管理员**：此类用户拥有对 Experience Platform Launch 中所有功能的完全访问权限，包括发布权限、创建容器和访问用户权限。此类用户不一定得是程序员，但若能掌握 HTML、CSS 和 JavaScript 的入门级或更高级别的知识，将有助于他们开展工作。为在您的网站上实施 Experience Platform Launch 代码，此类用户需要与贵组织的网站所有者合作。请至少确定一位负责贵组织实施的用户，该用户可以邀请其他 Experience Platform Launch 管理员。
- **网站所有者**：网站所有者可以是个人或团队，负责网站的编码和开发工作。他们不需要具有 Experience Platform Launch 帐户，但需要与 Experience Platform Launch 管理员合作，以获取 Experience Platform Launch 代码并在您的网站上实施该代码。
- **最终用户**：最终用户一般负责查看报表并寻找业务问题的答案。Analytics 管理员会向最终用户授予产品使用权限。

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

## 授予 Experience Platform Launch 的产品管理员访问权限

Experience Platform Launch 产品管理员访问权限的授予方式几乎与 Analytics 产品管理员访问权限几乎一模一样。

1. 使用您的 Adobe ID 凭据登录到 Admin Console。
1. 单击顶部的“产品”选项卡。贵组织购买的所有产品都位于左侧。单击“Experience Platform Launch by Adobe”，然后单击“新建配置文件”按钮。
1. 将此配置文件命名为“Experience Platform Launch 完全管理员访问权限”，然后单击“完成”。
1. 返回至“产品配置文件”页面，单击新建的配置文件，然后单击“权限”选项卡。
1. 单击任一权限行项。如果“自动包含”可用，请启用该项。如果“自动包含”不可用，请单击“全部添加”项。这两个选项都会将权限项移到右列。
1. 单击“保存”。对所有权限类别重复上述步骤。
1. 为配置文件授予所有类别的权限后，单击顶部的“概述”，以返回至“概述”页面。
1. 在“Experience Platform Launch by Adobe”图标下，单击“指定用户”。
1. 输入要向其授予 Analytics 完全访问权限的电子邮件地址，并为其分配新创建的具有完全管理员访问权限的配置文件。单击“保存”。
1. 此时，用户将拥有对 Experience Platform Launch 的完全访问权限。

## 后续步骤

[创建报表包](create-report-suite.md)：让您的 Analytics 管理员登录到该工具，并创建用于收集数据的报表包

[在 Experience Platform Launch 中创建资产](/help/implement/launch/create-analytics-property.md)：让您的 Experience Platform Launch 管理员登录到该工具，并创建要在您的站点上实施的资产
