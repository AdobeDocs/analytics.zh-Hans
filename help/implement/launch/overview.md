---
title: 在Adobe Experience Platform中使用标记实施
description: 了解如何使用标记实施Adobe Analytics
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 43%

---

# 在Adobe Experience Platform中使用标记实施

>[!NOTE]
>Adobe Experience Platform Launch已在Experience Platform中被重新命名为一套数据收集技术。 因此，在产品文档中推出了一些术语更改。 有关术语更改的统一参考，请参阅以下[文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

在 Adobe Analytics 的整个生命周期中，Adobe 提供了多种不同方法来帮助您在网站上实施用于收集数据的代码。Adobe当前的推荐方法是通过Adobe Experience Platform中的标记。

Adobe Experience Platform数据收集中的标记是一个标签管理解决方案，它允许您在部署Analytics代码的同时满足其他标记要求。 Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。

拥有有效Adobe Experience Cloud合同的所有客户都可以使用标记。 如果不确定您是否具有所需访问权限，请联系贵组织的 Experience Cloud 系统管理员。

## 整个工作流

使用标记运行实施应遵循以下步骤：

1. **获取对标记的访问权限**:您可以通过组织中的系统管理员获取对Platform标记的访问权限。
2. **创建标记属性**:属性是用于引用标签管理数据的总容器。
3. **部署到开发环境**：有一个可在其中进行标签迭代开发的环境。
4. **验证并发布到生产环境**：确保一切正常，然后将其实时发布。

要开始操作，请参阅[创建Analytics标记属性](create-analytics-property.md) 。

## 其他资源

可以高度自定义标记。 详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

* [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#):了解界面的工作方式和可用的扩展。
* [Adobe Analytics 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en)：使用 Analytics 扩展将数据发送到 Adobe Analytics。
* [实施变量](../vars/overview.md)：确定要发送到数据收集服务器的变量。
