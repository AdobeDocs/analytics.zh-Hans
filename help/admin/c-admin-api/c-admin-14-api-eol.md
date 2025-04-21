---
description: Adobe Analytics 1.4 API生命周期结束公告的详细信息。
title: Adobe Analytics 1.4 API EOL FAQ
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Adobe Analytics 1.4 API EOL FAQ

Adobe计划于&#x200B;**2026年8月12日**&#x200B;停用Adobe Analytics 1.4 API。 在此日期之后将无法再访问它们。 此公告将直接影响以下内容：

* Adobe Analytics 1.4 API，不包括数据插入API
* Adobe Analytics WSSE 身份验证

## 1.4 API

[Adobe Analytics 1.4 API](https://developer.adobe.com/analytics-apis/docs/1.4/)提供了范围广泛的操作，如报表、分类、数据馈送和报表包配置。 它们即将弃用，而支持[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。 2.0 API允许您执行几乎所有可以在Analytics用户界面中执行的操作，例如报告或管理区段和计算量度等组件。

Adobe为1.4 API用户提供了[迁移路径](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/)。 您可以将集成迁移到2.0 API(与Adobe Analytics应用程序所依赖的API相同)并利用最新功能。 1.4 API中可用的任何功能都可以使用[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)实现。

## WSSE身份验证

WSSE身份验证是Analytics 1.4 API支持的旧版身份验证协议。 已由[Adobe Developer Console](https://developer.adobe.com/console/home)中提供的基于OAuth的身份验证选项取代。 使用WSSE身份验证的项目必须将其凭据更新为Adobe Developer Console中设置的凭据。 为此，请登录[Adobe Developer Console](https://developer.adobe.com/console/home)以创建您的Analytics 2.0 API集成项目。 选择OAuth用户或OAuth服务器到服务器身份验证方法。

## 常见问题解答

+++**这是否会影响我现有的Analytics API Adobe IO项目？**

任何使用Analytics 1.4 API的现有项目都会受到影响。 必须在EOL截止日期之前将这些集成迁移到[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)。

+++

+++**我已与使用Adobe API的其他产品或应用程序共享我的Analytics凭据。 他们是否会受到影响？**

如果该产品或应用程序使用您的WSSE凭据和/或调用Analytics 1.4 API，则会受到影响，并且必须在EOL截止日期之前迁移。 请联系产品或应用程序提供商，以获取有关其迁移计划和时间表的更多详细信息。

+++

+++**如何确定我的项目使用哪个API？**

API调用的基本URL决定了您的项目使用的API版本。 Adobe Analytics 1.4 API使用以下URL：
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

[Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)使用以下URL：

* `https://analytics.adobe.io`

如果您的任何API项目使用`api*.omniture.com`，则它使用Adobe Analytics 1.4 API，并且必须迁移到2.0 API。

+++

+++**此生命周期结束是否会影响数据收集？**

Adobe Analytics 1.4 EOL不会影响您的标记解决方案，例如标记(以前称为Adobe Launch)、Web SDK或AppMeasurement。 但是，如果您使用1.4数据源或分类API来增强数据，则必须将这些工作流迁移到Adobe Analytics 2.0 API。

此生命周期结束公告不影响Data Insertion API。 虽然Adobe计划继续支持数据插入API，但Adobe建议改用[批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。

+++

如果您对于本页面未回答的本生命周期结束公告存有其他问题，请联系您的Adobe客户团队。
