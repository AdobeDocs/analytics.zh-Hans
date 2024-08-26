---
description: Adobe Analytics 管理员 API 在 github 上的链接。
title: Adobe Analytics 1.4 API EOL FAQ
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 4%

---

# Adobe Analytics 1.4 API EOL FAQ

## 生命周期结束(EOL)通知

**即将弃用的内容？**

* Adobe Analytics 1.4 API

* Adobe Analytics WSSE 身份验证

**何时关闭它？**

这些服务将于2026年8月12日停用。 在此日期之后将无法再访问它们。

## 1.4 API

**这些服务是什么？**

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/)是API的集合，它提供了一系列操作，如报表、分类、数据馈送和报表包配置。

**我需要做什么才能迁移？**

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)为1.4 API用户提供迁移途径。 当前使用1.4 API的客户可以将其集成迁移到2.0 API(与Adobe Analytics应用程序所依赖的API相同)并利用最新功能。

2.0 API允许您执行几乎所有可以在Analytics用户界面中执行的操作，例如报告或管理区段和计算量度等组件。

**2.0 API是否提供与1.4 API相同的功能？**
1.4 API中可用的任何功能都可以使用[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)来完成。 某些功能提供的功能与1.4 API中提供的功能相同，具有相同的功能，可让您执行几乎所有可在Analytics用户界面中执行的操作，例如报告或管理区段和计算量度等组件。

## WSSE身份验证

**这些服务是什么？**

WSSE身份验证是Analytics 1.4 API支持的旧版身份验证协议。 已由[Adobe Developer Console](https://developer.adobe.com/console/home)中提供的基于OAuth的身份验证选项取代。

**我需要做什么才能迁移？**

WSSE客户必须更新其身份验证，才能使用Adobe Developer Console中设置的凭据。 为此，请登录[Adobe Developer Console](https://developer.adobe.com/console/home)以创建您的Analytics 2.0 API集成项目。 在OAuth用户和OAuth服务器到服务器身份验证方法之间选择。

## 问题

问：**这是否会影响我现有的Analytics APIAdobeIO项目？**

答：任何使用Analytics 1.4 API的现有项目都将受到影响。 必须在EOL截止日期之前将这些集成迁移到[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

问：**我已与使用Analytics API的其他产品或应用程序共享我的Adobe凭据。 他们是否会受到影响？**

答：如果该产品或应用程序使用您的WSSE凭据和/或调用Analytics 1.4 API，则会受到影响，并且需要在EOL截止日期之前进行迁移。 请联系产品或应用程序提供商，以获取有关其迁移计划和时间表的更多详细信息。

问：**我不确定我们正在使用哪个Adobe Analytics API。**

答：您可以通过集成中调用的地址来识别您正在使用的API。

通过调用以下任意URL访问Adobe Analytics 1.4 API：
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

通过调用以下URL访问[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)：
* https://analytics.adobe.io

如果您使用的是api*.omniture.com，则需要迁移到[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

问：**Adobe Analytics 2.0 API是否与1.4 API相同？ 如果没有，最大的区别是什么？**

答：Adobe Analytics 2.0 API与1.4 API并不完全相同，但它们提供的功能是相当的，包括以下好处：

* 更快的响应时间，更简单、更高效的查询方法，无需轮询

* 用于查询和动态报告更新的编程功能

* 更优雅的错误处理

* 灵活的功能，可完成您可以从Analysis Workspace完成的任何任务

* API调用与UI操作的一致性和匹配

* 访问Analysis Workspace中使用的所有Attribution IQ模型

* 访问Analysis Workspace中使用的所有异常检测算法

* 能够与其他Experience Cloud产品集成

* 增加了多个划分报告的容量

* 访问最新的Analytics功能

“[迁移到Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/)”指南讨论了1.4和2.0 API之间的主要区别。 [Analytics 2.0 API常见问题解答](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/)中还提供了其他信息。

问：**这是否会影响数据收集？**

答：Adobe Analytics 1.4 EOL不会影响您的标记解决方案，例如Tags(以前称为AdobeLaunch)、WebSDK或AppMeasurement.js。 但是，如果您使用1.4数据源或分类API收集或增强数据，则必须将这些工作流迁移到Adobe Analytics 2.0 API。 有关更多详细信息，请参阅[2.0 API端点指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/)。

问：**数据插入API是否受到影响？**

答：否，数据插入API不受Adobe Analytics 1.4 EOL的影响。

问：**如果我的问题没有在这个FAQ中回答，该怎么办？**

答：如果您仍有疑问，请联系您的Adobe客户代表。
