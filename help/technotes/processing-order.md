---
title: 处理Adobe Analytics中数据的顺序
description: 了解在Adobe Analytics中处理数据的组件和服务的顺序。
source-git-commit: 65ee7ae6d838f34149eb60547d976856e4da3b17
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# 处理Adobe Analytics中数据的顺序

Adobe提供了多种方法来更改或处理数据，然后才会在报表中显示。 本页显示各种Adobe Analytics功能处理数据的顺序。 您可以使用此列表排除数据不一致的问题，或确定在需要进行数据调整时使用的最佳功能。

## 数据在发送到Adobe之前

在将数据发送到Adobe之前，通常使用以下方法之一在客户端进行编译：

* **AppMeasurement**:在您的网站上托管并在每个页面上引用的JavaScript文件。 数据会直接发送到Adobe Analytics。
* **Adobe Experience Platform Web SDK**:在您的网站上托管并在每个页面上引用的JavaScript文件。 数据会发送到Adobe Experience Edge。
* **Adobe Experience Cloud数据收集中的标记**:每个页面上的JavaScript引用，其中包含在数据收集UI中创建的规则。 Adobe Analytics扩展提供了一种更轻松的AppMeasurement实施方法。 Web SDK扩展提供了一种更轻松的Web SDK实施方法。

如果您将数据发送到Adobe Experience Edge，则可以对其进行配置，以将数据转发到Adobe Analytics(以及许多其他Adobe Experience Cloud解决方案)。 无论采用何种实施方法，最终都会向Adobe数据收集服务器发送包含所需变量的图像请求。

## 数据到达Adobe Analytics数据收集服务器时

数据到达Adobe Analytics后，以下功能会根据需要调整数据：

1. **查找表**:Dimension依赖于Adobe内部查找表(例如， [浏览器](/help/components/dimensions/browser.md) 维度)与其相应值匹配。
2. [**动态变量**](/help/implement/vars/page-vars/dynamic-variables.md):如果在图像请求的任何部分中都看到动态变量，则会复制该值，并将其视为独立值，随后会将其视为独立值。
3. [**机器人规则**](/help/admin/admin/bot-removal/bot-rules.md):应用标准或自定义机器人过滤，以从报表中排除该数据。
4. [**处理规则**](/help/admin/admin/c-processing-rules/processing-rules.md):您的组织应用于您数据的自定义规则。 包括 [上下文数据变量](/help/implement/vars/page-vars/contextdata.md) 到相应的变量。
5. **VISTA规则**:由Adobe顾问应用于您数据的自定义灵活规则。 VISTA规则可能会在处理规则之前或之后运行，具体取决于贵组织的需求。 大多数VISTA规则通常在处理规则之后运行，但每个组织的设置方式不同。 有关现有VISTA规则的更多信息，请联系您的Adobe客户经理。
6. [**营销渠道处理规则**](/help/components/c-marketing-channels/c-rules.md):您可以使用 [处理规则](/help/admin/admin/c-processing-rules/processing-rules.md) 以准备数据以在营销渠道处理规则中使用。
7. **地理位置数据**:依赖IP地址查找的Dimension(例如， [国家/地区](/help/components/dimensions/countries.md) 维度)。
8. [**IP模糊处理**](/help/admin/admin/general-acct-settings-admin.md):如果贵组织已选择对原始数据中的IP地址进行模糊处理，则在完成所有其他处理功能后即可完成。

此时，单个点击将记录在报表包数据表中。 在标准之后 [延迟](latency.md) 间隔时，它在报表中可用。

## 处理数据后更改数据

Adobe Analytics的数据大多是永久性的；但是，有一些功能允许选择性地调整或删除数据：

* [**数据修复API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/):编辑某些列或删除所需的数据行。
* [**数据管理**](/help/admin/c-data-governance/an-gdpr-workflow.md):处理隐私请求以永久删除数据。
* [**分类**](/help/components/classifications/c-classifications.md):根据规则或上传的数据创建维度，以便以不同方式组织数据。 基础报表包数据不会发生更改，因此您可以自由编辑或覆盖分类数据。
* [**虚拟报表包**](/help/components/vrs/vrs-about.md):创建可更改访问超时或允许的替代报表包视图 [跨设备分析](/help/components/cda/overview.md).
