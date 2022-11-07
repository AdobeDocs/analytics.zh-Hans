---
title: 在Adobe Analytics中使用标记实施Adobe Experience Platform
description: 了解如何使用标记实施 Adobe Analytics
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 94%

---

# 在Adobe Analytics中使用标记实施Adobe Experience Platform

在 Adobe Analytics 的整个生命周期中，Adobe 提供了多种不同方法来帮助您在网站上实施用于收集数据的代码。Adobe 目前推荐的方法是使用 Adobe Experience Platform 中的标记进行实施。

Adobe Experience Platform 中的标记是一款标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。

凡是已签署有效 Adobe Experience Cloud 合同的客户都可以使用标记。如果不确定您是否具有所需访问权限，请联系贵组织的 Experience Cloud 系统管理员。

## 整个工作流

使用标记运行实施应遵循如下步骤：

1. **获取对标记的访问权限**：您可以通过组织的系统管理员获取对 Platform 标记的访问权限。
2. **创建标记属性**：属性是用于引用标记管理数据的总容器。
3. **部署到开发环境**：有一个可在其中进行标签迭代开发的环境。
4. **验证并发布到生产环境**：确保一切正常，然后将其实时发布。

请参阅[创建 Analytics 标记属性](create-analytics-property.md)以开始使用。

## 其他资源

标记可高度定制。详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

* [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)：了解界面的使用方式和可用的扩展。
* [Adobe Analytics 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=zh-Hans)：使用 Analytics 扩展将数据发送到 Adobe Analytics。
* [实施变量](../vars/overview.md)：确定要发送到数据收集服务器的变量。
