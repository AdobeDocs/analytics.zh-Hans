---
description: Adobe Audience Manager (Adobe Audience Manager)是一个功能强大的数据管理平台，可帮助您从第一方、第二方/合作伙伴和第三方数据集成构建独一无二的受众配置文件。 对广告商而言，这些受众配置文件有助于定义要跨任何数字渠道使用的最有价值的区段。
solution: Experience Cloud
title: Audience Analytics 概述
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 42%

---

# Audience Analytics 概述

Adobe Audience Manager (Adobe Audience Manager)是一个功能强大的数据管理平台，可帮助您从第一方、第二方/合作伙伴和第三方数据集成构建独一无二的受众配置文件。 对广告商而言，这些受众配置文件有助于定义要跨任何数字渠道使用的最有价值的区段。

通过实施Audience Analytics集成，您可以将诸如人口统计信息（如性别或收入水平）、心理统计信息（如兴趣和爱好）、CRM数据和广告展示数据之类的Adobe Audience Manager受众数据合并到任何Analytics工作流程中。

>[!VIDEO](https://video.tv.adobe.com/v/25450/?quality=12)

## 主要优势 {#benefits}

Audience Analytics 集成功能具有以下主要优点：

* 它是数据管理平台 (DMP) 和市场上的分析引擎之间的第一次产品化集成。
* 区段可实时从Adobe Audience Manager共享到Analytics，以告知受众发现、分段和优化。
* 默认情况下共享所有Adobe Audience Manager区段，从而完全丰富Analytics中的客户配置文件。
* 解决方案管理员只需极少的代码更改即可通过用户界面启用集成。
* 仅共享符合 Audience Manager 数据导出控件要求的区段。

## Audience Analytics的工作原理 {#works}

![](assets/mc-aud-dataflow.png)

1. 每当访客访问您的数字属性时，都会收集点击量并将其发送给 Analytics。
1. 通过[服务器端转发](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)，Analytics收到的每次点击都会实时自动发送到Adobe Audience Manager。
1. 通过Audience Analytics集成，对于每次点击，均会在Adobe Audience Manager中查找访客的受众成员资格，并将区段ID列表返回到Analytics以便实时处理。

由于Adobe Audience Manager区段是在同一次点击的基础上插入的，因此您可以确保Adobe Audience Manager中有关某个访客的所有可用数据都不会丢失并且会保持该点击的最新状态。 由于插件只能在下一次点击（而不是当前点击）时提供这些区段，因此这种方式要优于 AppMeasurement 插件。

此外，我们会自动将Adobe Audience Manager区段ID分类为其易记名称，以便您不必在Analytics报表中查看字母数字ID。

## 先决条件 {#prerequisites}

请确保满足以下先决条件：

* 您既是 Audience Manager 的客户，也是 Adobe Analytics 的客户。
* 您是 Audience Manager 管理员。
* 您使用的是 Identity Service v1.5 或更高版本。
* Adobe Audience Manager和Adobe Analytics报表包已映射到相同的Experience Cloud组织。
* 您使用[服务器端转发](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)并实施了[受众管理模块](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)（不是 DIL 代码）- AppMeasurement 1.5 或更高版本。

[Audience Analytics 工作流程](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)中介绍了这些先决条件。
