---
title: Adobe Analytics 中的 VISTA 规则
description: 详细了解 VISTA 规则及其功能。
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 57%

---

# Adobe Analytics 中的 VISTA 规则

VISTA 规则是可在数据收集和处理之间应用的自定义数据修改的另一种形式。请参阅[处理顺序](processing-order.md)，详细了解 VISTA 规则适用的数据管道中确切阶段。VISTA 规则仅影响正在收集的数据；它不会更改现有数据。

VISTA 规则的一些常见用例包括：

* 将 Analytics 点击从一个报表包复制到另一个报表包，可以选择将数据更改为复制的报表包
* 自定义 IP 排除，超出了由[通过 IP 排除](/help/admin/tools/exclude-ip.md)提供的用例
* 有条件地或全局修改任何变量值
* 将变量值复制到其他变量
* 将可能影响变量值的文件上传到 Adobe FTP 站点

VISTA 规则的许多用例已由[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)、[机器人规则](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)、[虚拟报表包](/help/components/vrs/vrs-about.md)提供，或只是更新您的 Adobe Analytics 实施。Adobe 建议只有在万不得已时才使用 VISTA 规则。

>[!IMPORTANT]
>
>VISTA规则实施和配置需要贵组织与Adobe Professional Services之间签订付费协议。 如果要创建或更新VISTA规则，请联系您的Adobe客户团队。
>
>请注意：
>
>* VISTA规则创建仅包括初始实施。 持续维护或VISTA规则更新需要单独的付费参与。
>
>* VISTA规则取决于数据中的特定条件。 例如，更改Adobe Analytics实施、收集的数据类型或字符串长度、更改用于DB VISTA的表或对输入数据模式进行其他更改可能会导致VISTA规则停止按预期运行。 Adobe建议定期审查VISTA规则，以确定是否需要更新或删除。

## 创建 VISTA 规则 {#create}

您必须使用 Adobe Professional Services 才能创建 VISTA 规则。如果要创建VISTA规则，请联系您的Adobe客户团队。

## 查看现有 VISTA 规则 {#see}

Adobe 不提供用于查看现有 VISTA 规则的 UI。联系您的Adobe客户团队或客户关怀团队，获得所需的报表包以检索现有VISTA规则的列表。
