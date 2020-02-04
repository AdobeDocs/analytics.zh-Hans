---
title: 使用Launch概述实施
description: 了解如何使用Adobe Experience Platform Launch实施Adobe Analytics
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# 使用Launch概述实施

在Adobe Analytics的整个生命周期中，Adobe提供了多种不同的方法在您的网站上实施代码以收集数据。 Adobe目前推荐的方法是通过Adobe Experience Platform Launch。

Launch是一款标签管理解决方案，可让您在部署Analytics代码的同时部署其他标签要求。 Adobe提供与其他解决方案和产品的集成，并允许您部署自定义代码。 所有这些任务都可以完成，无需依赖组织中的任何开发团队更新站点上的代码。

拥有有效Adobe Experience cloud合同的所有客户都可以使用Launch。 如果不确定您是否有权访问，请与贵组织的某个Experience cloud系统管理员联系。

## 整体工作流程

使用Launch运行实施的步骤如下：

1. **获取对Launch的访问权限**:您可以通过组织中的系统管理员获取对Launch的访问权限。
2. **创建属性**:属性是用于引用标签管理数据的总体容器。
3. **部署到开发环境**:有一个环境，您可以在其中对标签的开发进行迭代。
4. **验证并发布到生产**:确保一切正常，然后实时发布。

请参 [阅在Adobe Experience Platform Launch中创建Analytics属性](create-analytics-property.md) ，开始使用。

## 其他资源

Launch可以高度自定义。 进一步了解如何通过在实施中包含正确的数据来充分利用Adobe Analytics。

* [启动文档](https://docs.adobe.com/content/help/en/launch/using/overview.html):了解界面的工作方式和可用的扩展。
* [Adobe Analytics扩展](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html):使用Analytics扩展将数据发送到Adobe Analytics。
* [实施变量](../vars/overview.md):确定要发送到数据收集服务器的变量。
