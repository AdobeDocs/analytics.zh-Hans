---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Adobe Analytics中的产品配置文件

产品配置文件是可向组织内的用户分配的产品管理员的权限预设。如果您创建产品配置文件并将Experience Cloud用户分配到该产品配置文件，则它们将继承产品配置文件中包含的权限项目。

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## 产品配置管理员

产品配置文件管理员是可选组，可将用户添加或删除该产品配置文件。请注意，产品配置管理员与产品管理员不相同：

* 产品配置管理员仅负责对产品配置文件的用户列表负责。
* 产品配置管理员无权完全访问Adobe Analytics。为产品管理员保留对Adobe Analytics的完全访问权限。
* 产品配置管理员无法调整其产品配置文件中的权限项目；产品管理员必须进行权限项目调整。
* 产品配置管理员是团队潜在客户或管理者，他们只需为他们的团队授予和管理Adobe Analytics的访问权限。个人不需要使用系统管理员或产品管理员来授予对Adobe Analytics的访问权限。

## Adobe Analytics权限项目

用于访问Adobe Analytics的产品配置中所需的最低权限如下所示：

* 产品配置文件必须至少有权访问一个报告套件
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### 报表包

授予访问属于您的Analytics组织的报表包的权限。用户必须属于至少一个报告包才能获得使用Adobe Analytics的权限。

### 量度

授予访问报表包中的指标的权限。量度作为其在Analysis Workspace中的对应组件列出，或者如果该指标在Reports&amp; Analytics中可用，则在站点量度下作为菜单项可用。

自定义指标被标记为“自定义事件1-1000”，以使其独立于报告套件。如果“自定义事件1”是启用的权限项，则该用户可访问产品配置文件中所有报告包中的event1。

### 维度

授予访问报表包中的维度的权限。维度在Analysis Workspace中列出，或者如果维度在Reports&amp; Analytics中可用，则可以作为菜单项提供。

自定义变量(如eVar)被标记为“自定义转换1-250”，以使其独立于报表包。如果“自定义转换1”是启用的权限项，则该用户可在产品配置文件中的所有报告包中访问eVar1。

### 报表包工具

报表包工具权限项目允许访问特定于用户有权访问的报表包的功能。See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Analytics 工具

Analytics工具权限项目允许访问与报表包设置无关的功能。See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## 产品配置开发人员

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
