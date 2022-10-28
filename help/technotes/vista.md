---
title: Adobe Analytics中的VISTA规则
description: 进一步了解VISTA规则及其功能。
source-git-commit: 1e2284fd4a62816b27b33a91f3bee2575a852107
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# Adobe Analytics中的VISTA规则

VISTA规则是自定义数据修改的替代形式，您可以在数据收集和处理之间应用该格式。 请参阅 [处理顺序](processing-order.md) 有关VISTA规则所应用的数据管道中确切阶段的详细信息。 VISTA规则仅会在收集时影响当前数据；它不会更改现有数据。

VISTA规则的一些常见用例包括：

* 将Analytics点击从一个报表包复制到另一个报表包，或者将数据更改到复制的报表包
* 自定义IP排除超出了 [按IP排除](/help/admin/admin/exclude-ip.md)
* 有条件地或全局修改任何变量值
* 将变量值复制到其他变量
* 将文件上传到可能影响变量值的AdobeFTP站点

VISTA规则的许多用例已由 [处理规则](/help/admin/admin/c-processing-rules/processing-rules.md), [机器人规则](/help/admin/admin/bot-removal/bot-rules.md), [虚拟报表包](/help/components/vrs/vrs-about.md)，或者只是更新Adobe Analytics实施。 Adobe仅建议最后使用VISTA规则。

>[!IMPORTANT]
>
>VISTA规则要求贵组织与Adobe Professional Services之间签订付费协议。 如果要创建或更新VISTA规则，请联系贵组织的Adobe客户经理。

## 创建VISTA规则

您必须与Adobe Professional Services合作才能创建VISTA规则。 如果要创建VISTA规则，请联系贵组织的Adobe客户经理。

## 查看现有VISTA规则

Adobe不提供用于查看现有VISTA规则的UI。 使用所需的报表包与贵组织的Adobe客户经理或客户关怀团队联系，以检索现有VISTA规则的列表。
