---
title: Adobe Analytics 中处理数据的顺序
description: 了解在 Adobe Analytics 中处理数据的组件和服务的顺序。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 91%

---

# Adobe Analytics 中处理数据的顺序

Adobe 提供多种方式，可在报表中出现数据之前更改或操纵数据。此页面展示各项 Adobe Analytics 功能处理数据的顺序。可使用此列表解决数据不一致的问题或确定最适合在需要调整数据时使用的功能。

![处理顺序](assets/processing-order.png)

## 将数据发送到 Adobe 之前

将数据发送到 Adobe 之前，自动使用以下方法之一在客户端编译数据：

* **AppMeasurement**：一个托管在您的站点上并在每个页面上都引用的 JavaScript 文件。数据直接发送到 Adobe Analytics。
* **Adobe Experience Platform Web SDK**：一个托管在您的站点上并在每个页面上都引用的 JavaScript 文件。数据发送到Adobe Experience Platform Edge Network。
* **Adobe Experience Cloud Data Collection 中的标记**：一个在每个页面上都引用的 JavaScript 文件，其中包含在 Data Collection UI 中创建的规则。Adobe Analytics 扩展提供一种更容易实施 AppMeasurement 的方式。Web SDK 扩展提供一种更容易实施 Web SDK 的方式。

如果将数据发送到Edge Network，则可将其配置为将数据转发到Adobe Analytics(以及许多其他Adobe Experience Cloud解决方案)。 无论何种实施方法，最终都是将一个具有所需变量的图像请求发送到 Adobe 数据收集服务器。

## 数据到达 Adobe Analytics 数据收集服务器

一旦数据到达 Adobe Analytics，以下功能即按需调整数据：

1. **查找表**：依赖于 Adobe 内部查找表的维度（例如[浏览器](/help/components/dimensions/browser.md)维度）与其相应的值相配。
2. [**动态变量**](/help/implement/vars/page-vars/dynamic-variables.md)：如果在图像请求的任何部分中发现动态变量，则将其值复制过来，并且以后它其视为独立的值。
3. [**机器人规则**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)：应用标准或自定义机器人筛选以从报表中排除这些数据。
4. [**处理规则**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)：您的组织应用于您的数据的自定义规则。包括[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)与其相应变量的映射。
5. **VISTA 规则**：Adobe 顾问应用于您的数据的自定义灵活规则。可在处理规则前后运行 VISTA 规则，具体取决于您组织的需要。大多数 VISTA 规则一般都在处理规则之后运行，但每个组织的设置有所不同。有关现有VISTA规则的更多信息，请与您的Adobe客户团队联系。
6. [**营销渠道处理规则**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)：可使用[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)准备要用于营销渠道处理规则中的数据。
7. **地理位置数据**：填充依赖于 IP 地址查找的维度（例如[国家/地区](/help/components/dimensions/countries.md)维度）。
8. [**IP 混淆**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)：如果您的组织已决定混淆原始数据中的 IP 地址，则将在所有其他处理功能均已执行完毕后再混淆。

此时，将这次单独的点击记录在报表包数据表中。在标准[延迟](latency.md)间隔过后，可在报表中找到它。

## 处理数据之后更改数据

Adobe Analytics 中的数据大多为永久数据；但是，通过某些功能可选择性地调整或删除数据：

* [**数据修复 API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：编辑数据的某些列或删除数据中所需的行。
* [**数据治理**](/help/admin/admin/c-data-governance/an-gdpr-workflow.md)：考虑到隐私请求而永久删除数据。
* [**分类**](/help/components/classifications/c-classifications.md)：根据规则或上传的数据创建维度，这样使您可按不同方式组织数据。不更改报表套件的底层数据，因此您可随意编辑或覆盖分类数据。
* [**虚拟报表包**](/help/components/vrs/vrs-about.md)：创建可更改访问超时的备用报表包视图或允许[跨设备分析](/help/components/cda/overview.md)。
