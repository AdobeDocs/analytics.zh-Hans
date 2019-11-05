---
title: Adobe Analytics 管理入门指南
seo-title: Adobe Analytics 管理入门指南
description: 了解如何开始使用Adobe Analytics、常规角色类型和登录UI。
seo-description: 了解如何开始使用Adobe Analytics、常规角色类型和登录UI。
translation-type: tm+mt
source-git-commit: 4e3e164f5c28290ac280343d95cf5cb1186e09cd

---


# Adobe Analytics 管理入门指南

第一个管理员是组织内其他成员使用每个Experience cloud解决方案的起点。 签署合同后，Adobe的供应团队会准备创建该帐户。 第一个管理员在合同的开始日期之前会收到一封包含登录凭据的电子邮件。 强烈建议确保向Adobe提供第一个管理员的联系信息，并在签署合同前准确无误。

## 使用Experience cloud的关键角色

如果您的组织已购买Adobe Analytics，可考虑以下几个关键角色：

- **** Adobe Analytics管理员：这些用户对Adobe Analytics中的所有功能（包括报表包设置和用户权限）具有完全访问权限。 根据您的组织结构，不同的人员或团队可以负责Analytics管理的不同方面。 例如，一个人负责指定在实施中使用的变量。 另一个人可以负责确保每个人都具有正确的权限，从而使用户能够正确提取报告。 确定至少一位可负责Analytics报表包设置和用户权限的用户，并可从那里邀请其他Analytics管理员。
- **** Adobe Experience Platform Launch管理员：这些用户对Experience Platform Launch中的所有功能（包括发布权限、创建容器和用户权限）具有完全访问权限。 这些用户不一定是程序员，但至少拥有HTML、CSS和JavaScript的初学者知识是有益的。 他们负责与贵组织的网站所有者合作，在您的网站上实施Experience Platform Launch代码。 确定至少一位可负责贵组织实施的用户，并可从那里邀请其他Experience Platform Launch管理员。
- **** 网站所有者：这些个人或团队负责网站的编码和开发。 他们不需要帐户，但希望与Experience Platform Launch管理员合作获取Experience Platform Launch代码并在您的网站上实施它。
- **** 最终用户：这些用户通常查看报告并寻找业务问题的答案。 分析管理员授予这些用户在产品中工作的权限。

作为第一个管理员，您的角色可以在这些角色中的一个或多个角色中重叠。 只要涵盖了这些基本职责，您就可以授予权限，让组织中的其他人开始工作。

## 授予Analytics的产品管理员访问权限

系统级管理员无法直接访问产品，但是，他们可以通过添加自己为产品级管理员来授予自己访问权限。 如果您希望自己或其他人有权访问Adobe Analytics，您可以执行以下步骤。

1. 使用您的Adobe ID凭 [据登录到Admin Console](https://adminconsole.adobe.com/) 。
1. 单击顶部的“产品”选项卡。 您的组织购买的所有产品都位于左侧。 单击Adobe Analytics，然后单击“新建配置文件”按钮。
1. 将此配置文件命名为“Analytics完全管理员访问权限”，然后单击完成。
1. 返回至“产品配置文件”页面，单击新创建的配置文件，然后单击“权限”选项卡。
1. 单击其中一个权限行项目。 如果“自动包含”可用，请启用它。 如果“自动包含”不可用，请单击“全部添加”。 这两个选项都会将所有权限项目移到右列。
1. 单击“保存”。 对所有权限类别重复上述步骤。
1. 将所有权限类别授予配置文件后，单击顶部的“概述”，返回“概述”页面。
1. 在Adobe Analytics拼贴下，单击“分配用户”。
1. 输入要授予Analytics完全访问权限的电子邮件地址，并为其分配新创建的完全管理员访问权限配置文件。 单击“保存”。
1. 用户现在可以完全访问Adobe Analytics。

## 授予Experience Platform Launch的产品管理员访问权限

Experience Platform Launch的产品管理员访问权限与授予Analytics的产品管理员访问权限几乎相同。

1. 使用您的Adobe ID凭据登录到Admin Console。
1. 单击顶部的“产品”选项卡。 您的组织购买的所有产品都位于左侧。 单击“Experience Platform Launch by Adobe”，然后单击“新建配置文件”按钮。
1. 将此配置文件命名为“Experience Platform Launch完全管理员访问权限”，然后单击完成。
1. 返回至“产品配置文件”页面，单击新创建的配置文件，然后单击“权限”选项卡。
1. 单击其中一个权限行项目。 如果“自动包含”可用，请启用它。 如果“自动包含”不可用，请单击“全部添加”。 这两个选项都会将所有权限项目移到右列。
1. 单击“保存”。 对所有权限类别重复上述步骤。
1. 将所有权限类别授予配置文件后，单击顶部的“概述”，返回“概述”页面。
1. 在Experience Platform Launch by adobe拼贴下，单击“分配用户”。
1. 输入要授予Analytics完全访问权限的电子邮件地址，并为其分配新创建的完全管理员访问权限配置文件。 单击“保存”。
1. 用户现在可以完全访问Experience Platform Launch。

## 后续步骤

[创建报告套件](create-report-suite.md):让您的Analytics管理员登录到该工具并创建用于数据收集的报表包

[在Experience Platform Launch中创建属性](/help/implement/implement-with-launch/create-analytics-property.md):让您的Experience Platform Launch管理员登录到该工具并创建要在您的站点上实施的属性
