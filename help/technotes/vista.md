---
title: Adobe Analytics 中的 VISTA 规则
description: 详细了解 VISTA 规则及其功能。
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: ht
source-wordcount: '266'
ht-degree: 100%

---

# Adobe Analytics 中的 VISTA 规则

VISTA 规则是可在数据收集和处理之间应用的自定义数据修改的另一种形式。请参阅[处理顺序](processing-order.md)，详细了解 VISTA 规则适用的数据管道中确切阶段。VISTA 规则仅影响正在收集的数据；它不会更改现有数据。

VISTA 规则的一些常见用例包括：

* 将 Analytics 点击从一个报表包复制到另一个报表包，可以选择将数据更改为复制的报表包
* 自定义 IP 排除，超出了由[通过 IP 排除](/help/admin/admin/exclude-ip.md)提供的用例
* 有条件地或全局修改任何变量值
* 将变量值复制到其他变量
* 将可能影响变量值的文件上传到 Adobe FTP 站点

VISTA 规则的许多用例已由[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)、[机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)、[虚拟报表包](/help/components/vrs/vrs-about.md)提供，或只是更新您的 Adobe Analytics 实施。Adobe 建议只有在万不得已时才使用 VISTA 规则。

>[!IMPORTANT]
>
>VISTA 规则要求您的组织与 Adobe Professional Services 之间签订付费协议。如果您要创建或更新 VISTA 规则，请联系您组织的 Adobe 客户经理。

## 创建 VISTA 规则

您必须使用 Adobe Professional Services 才能创建 VISTA 规则。如果您要创建 VISTA 规则，请联系您组织的 Adobe 客户经理。

## 查看现有 VISTA 规则

Adobe 不提供用于查看现有 VISTA 规则的 UI。联系您组织的 Adobe 客户经理或客户关怀团队，获得所需的报表包以检索现有 VISTA 规则的列表。
