---
title: 基于字段的拼合
description: 了解使用基于字段的拼合来拼合数据的先决条件和限制。
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
source-git-commit: de8977e7ed7bf6bf93f75f608db34a7a3520ada7
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 83%

---

# 基于字段的拼合

{{available-existing-customers}}

Cross-Device Analytics 提供了两种截然不同的方法来拼合数据。此方法依靠 Analytics 变量（如 [prop](/help/implement/vars/page-vars/prop.md) 或 [eVar](/help/implement/vars/page-vars/evar.md)）包含人员标识符。它使用该变量作为将设备联系在一起的基础。Adobe 推荐此拼接选项，以提高访客跟踪的透明度和可预测性。

## 基于字段的拼合的特定先决条件

如果您打算使用基于字段的拼合来实施 Cross-Device Analytics，则需要满足以下条件。请与贵组织内的团队以及Adobe客户团队合作，确保您满足以下所有条件。

>[!WARNING]
>
>如果不满足所有先决条件，则可能会导致无法启用 Cross-Device Analytics，或者导致拼合数据时的结果不佳。

* [概述页面](overview.md)中列出了所有先决条件。
* 您的实施必须设置一个 prop 或 eVar，以便在可能的情况下（例如用户登录或打开电子邮件时）唯一标识个人。这项要求适用于所有平台，包括使用的移动应用程序。<br/>避免为此prop或eVar分配默认值。 如果为2,000台或更多不同设备分配了相同的默认值，则会将该人员添加到“坏人”列表中，并且这些事件将从启用CDA的虚拟报表包中删除，从而导致分析错误。
* 为基于字段的拼合配置所需的标识变量后，请将这些变量告知您的Adobe客户团队。

## 基于字段的拼合的特定限制

* 基于字段的拼接对于用户识别率/身份验证率较高的报表包效果最好。
* 虽然 prop 和 eVar 针对为报表用途处理大小写字符的方式都制定了规则，但基于字段的拼接不转换以任何方式用于拼接的 prop 或 eVar。基于字段的拼接使用指定字段中的值，因为它在 VISTA 规则之后和处理规则之后才存在。拼接过程区分大小写。例如，如果 prop/eVar 中有时出现“Bob”一词，有时出现“BOB”一词，则拼接过程将这两个词视为单独的两人。
* 鉴于基于字段的拼接区分大小写，因此 Adobe 建议复查适用于基于字段的拼接所使用的 prop 或 eVar 的任何 VISTA 规则或处理规则。需要复查它们以确保这些规则中的任何规则都不会引入同一 ID 的新形式。例如，应确保任何 VISTA 或处理规则都不会在仅一部分点击上将小写引入 prop 或 eVar。
* 基于字段的拼接不支持使用多个 prop 或 eVar 作拼接用途。例如，如果 eVar12 包含登录 ID，而 eVar20 包含电子邮件 ID，则必须二选其一。
* 基于字段的拼接不组合或连接多个字段（如 eVar10 + prop5）。
* prop 或 eVar 应仅包含一种类型的 ID。例如，prop 或 eVar 不应包含登录 ID 和电子邮件 ID 的组合。
* 如果对于同一访客发生了多次具有同一时间戳的点击，但拼接 prop 或 eVar 中的值不同，则 CDA 将根据字母顺序进行选择。因此，如果访客 A 具有时间戳相同的两次点击，其中一次点击指定 Bob，而另一次指定 Ann，则 CDA 将选择 Ann。


## 后续步骤

一旦您的组织符合所有要求并了解各种限制，您即可开始[设置 Cross-Device Analytics](setup.md)。
