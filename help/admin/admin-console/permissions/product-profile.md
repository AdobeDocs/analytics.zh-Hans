---
title: Adobe Analytics 的产品配置文件
description: 了解产品配置文件如何用作产品管理员可以分配给组织内的用户的权限预设。
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: ed7b25491de5c1238e846997ec903df4fd4ee18c
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 65%

---

# Adobe Analytics 的产品配置文件

产品配置文件是产品管理员可分配给组织内用户的权限预设。如果您创建产品配置文件并将其分配给 Experience Cloud 用户，用户将继承该产品配置文件中包含的权限项。

有关产品配置文件的一般信息，包括创建产品配置文件和分配用户，请参阅“企业用户指南”中的[管理企业用户的产品配置文件](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)。

## 产品配置文件管理员

产品配置文件管理员是一个可选组，可向相应产品配置文件添加用户或从中删除用户。请注意，产品配置文件管理员不同于产品管理员：

* 产品配置文件管理员没有 Adobe Analytics 的完全访问权限。而产品管理员拥有 Adobe Analytics 的完全访问权限。
* 产品配置文件管理员无法调整其产品配置文件中的权限项。
* 产品配置文件管理员可以向用户组分配或从中移除产品配置文件。
* 如果团队领导或经理需要为团队授予并管理 Adobe Analytics 的访问权限，那么产品配置文件管理员将是他们的不二之选。通过产品配置文件管理员，个人便无需麻烦系统管理员或产品管理员授予对 Adobe Analytics 的访问权限。

有关如何分配产品配置文件管理员的信息，请参阅《企业用户指南》的[管理企业用户的产品配置文件](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)一文中的“管理产品配置文件管理员”部分。

## Adobe Analytics 权限项

单个产品配置文件要访问Adobe Analytics所需的最低权限如下：

* 产品配置文件必须至少拥有一个报表包的访问权限
* 产品配置文件必须属于Analytics工具权限项&#x200B;**Analysis Workspace访问权限**。

### 报表包

授予对属于贵 Analytics 组织所有的报表包的访问权限。用户必须至少属于一个报表包，才能获得 Adobe Analytics 的使用权限。

### 量度

授予对报表包中量度的访问权限。这些指标将作为相应的组件在Analysis Workspace中列出。

自定义量度将标记为“自定义事件 1-1000”，以使其独立于报表包。如果“自定义事件 1”是已启用的权限项，则该用户有权访问产品配置文件中所有报表包中的 event1。

### 维度

授予对报表包中维度的访问权限。维度将作为相应的组件在Analysis Workspace中列出。

自定义变量（如 eVar）将标记为“自定义转化 1-250”，以使其独立于报表包。如果“自定义转化 1”是已启用的权限项，则该用户有权访问产品配置文件中所有报表包中的 eVar1。

### 报表包工具

报表包工具权限项用于授予对特定于用户可访问报表包的功能的访问权限。有关权限项及其说明的完整列表，请参阅[报表包工具](report-suite-tools.md)。

### Analytics 工具

Analytics 工具权限项用于授予对独立于报表包设置的功能的访问权限。有关权限项及其说明的完整列表，请参阅 [Analytics 工具的产品配置文件权限](analytics-tools.md)。

## 产品配置文件开发人员

开发人员类似于用户，只不过开发人员有权在Adobe Developer上使用Experience Cloud API。 有关更多信息，请参阅《企业用户指南》中的[管理开发人员](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。如果用户被授予任何配置文件的开发人员访问权限，他们将有权访问开发控制台(console.adobe.io)并编辑Adobe Analytics集成。 为用户授权的Analytics API调用和响应取决于用户有权访问的所有配置文件的净权限。

例如，凭借包含所有量度、所有维度和一个报表包的配置文件权限，开发人员可以发起与该报表包中的任何组件相关的API调用。 如果添加了异常检测权限项，则API响应可以包括异常数据。 根据经验，如果配置文件授予对Adobe Analytics界面中某个场景的访问权限，则开发人员对类似定义配置文件的访问权限将启用相应的API调用和响应。
