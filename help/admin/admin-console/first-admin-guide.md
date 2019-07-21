---
title: Adobe Analytics第一管理指南
seo-title: Adobe Analytics第一管理指南
description: 了解如何开始使用Adobe Analytics、一般角色类型以及登录UI。
seo-description: 了解如何开始使用Adobe Analytics、一般角色类型以及登录UI。
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Adobe Analytics第一管理指南

第一个管理员是允许组织其余部门使用每个Experience Cloud解决方案的起点。签署合同后，Adobe的供应团队将准备要创建的帐户。第一个管理员在合同开始日期之前收到带有登录凭据的电子邮件。强烈建议在强烈建议签署合同前向Adobe提供第一个管理员的联系信息。

## 使用Experience Cloud中的主要角色

如果您所在的组织购买了Adobe Analytics，则可以考虑以下几个主要角色：

- **Adobe Analytics管理员：** 这些用户可以完全访问Adobe Analytics中的所有内容，包括报告套件设置和用户权限。根据组织的构造方式，不同的人员或团队可以对Analytics管理的不同facet负责。例如，一个人负责指定要在实施中使用的变量。另一个人负责确保用户能够确保每个人具有正确的权限，从而使用户能够正确地提取报告。识别至少一个负责分析报告套件设置和用户权限的用户，他们可以从此处邀请其他Analytics管理员。
- **Adobe Experience Platform Launch管理员：** 这些用户可以完全访问Experience Platform Launch中的所有内容，包括发布权限、创建容器和用户权限。这些用户并不一定是程序员，但至少有初学者有关HTML、CSS和JavaScript的知识是很有用的。他们有责任与贵组织的网站所有者共同获得在您的站点上实施的Experience Platform Launch代码。确定至少一个负责组织实施的用户，他们可以从那里邀请其他Experience Platform Launch管理员。
- **网站所有者：** 这些个人或团队负责您的网站的编码和开发。他们不需要帐户，但要使用Experience Platform Launch管理员来获得Experience Platform Launch代码并在您的网站上实施它。
- **最终用户：** 这些用户通常查看报告并寻找业务问题的答案。Analytics管理员授予这些用户在产品中工作的权限。

作为第一个管理员，您的角色可以在其中一个或多个角色中重叠。只要涵盖其中的每一项基本职责，您都可以授予您的组织中的其他人启动和运行的权限。

## 授予Analytics产品管理员访问权限

系统级管理员无权直接访问产品，但他们可以通过将自己添加为产品级管理员来为自己提供访问权限。如果您希望自己或其他人访问Adobe Analytics，您可以遵循这些步骤。

1. Log in to the [Admin Console](https://adminconsole.adobe.com/) with your Adobe ID credentials.
1. 单击顶部的“产品”选项卡。您的组织购买的所有产品都位于左侧。单击Adobe Analytics，然后单击“新建配置文件”按钮。
1. 将此配置文件命名为“Analytics完全管理访问”，然后单击“完成”。
1. 返回产品配置文件页面，单击新建的配置文件，然后单击权限选项卡。
1. 单击其中一个权限行项目。如果“自动包含”可用，则启用它。如果自动包含不可用，请单击“添加全部”。这两个选项都将所有权限项目移动到右列。
1. 单击保存。对所有权限类别重复以上步骤。
1. 将所有权限类别授予配置文件后，请单击顶部的概述，返回概述页面。
1. 在Adobe Analytics拼贴下，单击“分配用户”。
1. 输入您希望对其授予完全Analytics访问权限的电子邮件地址，并为其分配新创建的完全管理访问配置文件。单击“保存”。
1. 用户现在可以完全访问Adobe Analytics。

## 为Experience Platform Launch授予产品管理员访问权限

Experience Platform Launch的产品管理员访问与授予Analytics产品管理员访问几乎相同。

1. 使用您的Adobe ID凭据登录到Admin Console。
1. 单击顶部的“产品”选项卡。您的组织购买的所有产品都位于左侧。单击Experience Platform Launch by Adobe，然后单击“New Profile”按钮。
1. 将此配置文件的“体验平台启动完全管理访问”命名为，然后单击完成。
1. 返回产品配置文件页面，单击新建的配置文件，然后单击权限选项卡。
1. 单击其中一个权限行项目。如果“自动包含”可用，则启用它。如果自动包含不可用，请单击“添加全部”。这两个选项都将所有权限项目移动到右列。
1. 单击保存。对所有权限类别重复以上步骤。
1. 将所有权限类别授予配置文件后，请单击顶部的概述，返回概述页面。
1. 在Experience Platform Launch by Adobe拼贴下，单击“分配用户”。
1. 输入您希望对其授予完全Analytics访问权限的电子邮件地址，并为其分配新创建的完全管理访问配置文件。单击“保存”。
1. 用户现在可以完全访问Experience Platform Launch。

## 后续步骤

[创建报表包](create-report-suite.md)：让Analytics管理员登录该工具并为数据收集创建报告套件

[在Experience Platform Launch中创建一个属性](../../implement/implement-with-launch/create-analytics-property.md)：让Experience Platform Launch管理员登录到工具并创建要在站点上实施的属性
