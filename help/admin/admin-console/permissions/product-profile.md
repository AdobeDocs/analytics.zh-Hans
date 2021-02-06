---
source-git-commit: 03b1195225b97f3ea151eb5b4f39fbed746b3654
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '646'
ht-degree: 67%

---
# Adobe Analytics产品用户档案

产品用户档案是产品管理员可以将权限预设分配给组织内的用户。 如果您创建产品配置文件并将其分配给 Experience Cloud 用户，用户将继承该产品配置文件中包含的权限项。

有关产品配置文件的一般信息，请参阅“企业用户指南”中的[管理产品和配置文件](https://helpx.adobe.com/cn/enterprise/using/manage-products-and-profiles.html)。

## 产品配置文件管理员

产品配置文件管理员是一个可选组，可向相应产品配置文件添加用户或从中删除用户。请注意，产品配置文件管理员不同于产品管理员：

* 产品配置文件管理员没有 Adobe Analytics 的完全访问权限。而产品管理员拥有 Adobe Analytics 的完全访问权限。
* 产品用户档案管理员可以调整其产品用户档案中的权限项目。
* 产品用户档案管理员可以向用户组分配或删除产品用户档案。
* 产品用户档案管理员是团队领导或需要授予和管理团队对Adobe Analytics的访问权限的经理的理想之选。 通过产品配置文件管理员，个人便无需麻烦系统管理员或产品管理员授予对 Adobe Analytics 的访问权限。

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

Analytics 工具权限项用于授予对独立于报表包设置的功能的访问权限。有关权限项目和说明的完整列表，请参阅[分析工具的产品用户档案权限](analytics-tools.md)。

## 产品配置文件开发人员

开发人员类似于用户，只不过开发人员有权在 Adobe I/O 上使用 Experience Cloud API。有关更多信息，请参阅“企业用户指南”中的[管理开发人员](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。如果用户被授予对任何用户档案的开发人员访问权限，则他们可以访问开发控制台(console.adobe.io)并编辑Adobe Analytics集成。 为用户授权的Analytics API调用和响应将取决于该用户具有开发人员访问权限的所有用户档案的净权限。

例如，用户档案权限包括所有指标、所有维和一个报表包，用户档案的开发人员访问成员可以发出与相关套件中的任何组件相关的API调用。 添加异常检测后，报告可能包含更完整的响应，从而添加异常数据。 作为经验法则，如果用户档案授予对Adobe Analytics界面中某个场景的访问权，则在类似定义的用户档案上的开发人员访问将启用相应的API调用和响应。
