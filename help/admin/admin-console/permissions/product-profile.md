---
title: Adobe Analytics 的产品配置文件
description: 了解产品配置文件如何用作产品管理员可以分配给组织内的用户的权限预设。
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
translation-type: ht
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: ht
source-wordcount: '671'
ht-degree: 100%

---

# Adobe Analytics 的产品配置文件

产品配置文件是产品管理员可分配给组织内用户的权限预设。如果您创建产品配置文件并将其分配给 Experience Cloud 用户，用户将继承该产品配置文件中包含的权限项。

有关产品配置文件的一般信息，请参阅“企业用户指南”中的[管理产品和配置文件](https://helpx.adobe.com/cn/enterprise/using/manage-products-and-profiles.html)。

## 产品配置文件管理员

产品配置文件管理员是一个可选组，可向相应产品配置文件添加用户或从中删除用户。请注意，产品配置文件管理员不同于产品管理员：

* 产品配置文件管理员没有 Adobe Analytics 的完全访问权限。而产品管理员拥有 Adobe Analytics 的完全访问权限。
* 产品配置文件管理员可以调整其产品配置文件中的权限项。
* 产品配置文件管理员可以向用户组分配或从中移除产品配置文件。
* 如果团队领导或经理需要为团队授予并管理 Adobe Analytics 的访问权限，那么产品配置文件管理员将是他们的不二之选。通过产品配置文件管理员，个人便无需麻烦系统管理员或产品管理员授予对 Adobe Analytics 的访问权限。

## Adobe Analytics 权限项

为能够访问 Adobe Analytics，产品配置文件中至少需要以下权限：

* 产品配置文件必须至少拥有一个报表包的访问权限
* 产品配置文件必须属于 Analytics 工具权限项 **Analysis Workspace 访问权限**（或 **Reports &amp; Analytics 访问权限**）

### 报表包

授予对属于贵 Analytics 组织所有的报表包的访问权限。用户必须至少属于一个报表包，才能获得 Adobe Analytics 的使用权限。

### 量度

授予对报表包中量度的访问权限。量度将作为相应的组件在 Analysis Workspace 中列出；或者，如果量度在 Reports &amp; Analytics 中可用，则将作为菜单项在“网站量度”下列出。

自定义量度将标记为“自定义事件 1-1000”，以使其独立于报表包。如果“自定义事件 1”是已启用的权限项，则该用户有权访问产品配置文件中所有报表包中的 event1。

### 维度

授予对报表包中维度的访问权限。维度将作为相应的组件在 Analysis Workspace 中列出；或者，如果维度在 Reports &amp; Analytics 中可用，则将作为菜单项列出。

自定义变量（如 eVar）将标记为“自定义转化 1-250”，以使其独立于报表包。如果“自定义转化 1”是已启用的权限项，则该用户有权访问产品配置文件中所有报表包中的 eVar1。

### 报表包工具

报表包工具权限项用于授予对特定于用户可访问报表包的功能的访问权限。有关权限项及其说明的完整列表，请参阅[报表包工具](report-suite-tools.md)。

### Analytics 工具

Analytics 工具权限项用于授予对独立于报表包设置的功能的访问权限。有关权限项及其说明的完整列表，请参阅 [Analytics 工具的产品配置文件权限](analytics-tools.md)。

## 产品配置文件开发人员

开发人员类似于用户，只不过开发人员有权在 Adobe I/O 上使用 Experience Cloud API。有关更多信息，请参阅“企业用户指南”中的[管理开发人员](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。如果授予用户任何配置文件的开发人员访问权限，则他们将有权访问开发控制台 (console.adobe.io) 并编辑 Adobe Analytics 集成。在用户拥有开发人员访问权限的所有配置文件中，这些配置文件的净权限决定了为该用户授予的 Analytics API 调用和响应。

例如，根据配置文件权限（包含所有量度、所有维度和一个报表包），持有配置文件开发人员访问权限的成员可发出与关联套件中任何组件相关的 API 调用。随着“异常检测”的添加，报告可以包含更完整的响应，从而添加异常数据。根据经验，如果配置文件授予对 Adobe Analytics 界面中某个场景的访问权限，则对类似定义的配置文件的开发人员访问权限将启用相应的 API 调用和响应。
