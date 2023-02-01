---
title: 使用Analytics扩展实施Adobe Analytics
description: 了解如何使用标记和Analytics扩展实施Adobe Analytics
feature: Launch Implementation
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 48%

---

# 使用Analytics扩展实施Adobe Analytics

在 Adobe Analytics 的整个生命周期中，Adobe 提供了多种不同方法来帮助您在网站上实施用于收集数据的代码。Adobe当前推荐的方法是在Adobe Experience Platform中通过标记。

Adobe Experience Platform 中的标记是一款标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。

凡是已签署有效 Adobe Experience Cloud 合同的客户都可以使用标记。如果不确定您是否具有所需访问权限，请联系贵组织的 Experience Cloud 系统管理员。

实施任务的高级概述：

![Adobe Analytics使用Analytics扩展工作流](../assets/analytics-extension-annotated.png)

|<div style="width:20px"></div>|任务 |更多信息 | |-|—|—| | 1 |确保您拥有 **定义了报表包**. | [报表包管理器](../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **创建数据层** 用于管理网站上数据的跟踪。 | [创建数据层](../prepare/data-layer.md) | | 3 | **创建标记属性**. 属性是用于引用标签管理数据的总容器。| [创建Adobe Analytics标记属性](../launch/create-analytics-property.md) | | 4 | **安装Analytics扩展** 在标记属性中。 配置Analytics扩展以将数据发送到Adobe Analytics。 | [Adobe Analytics扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en) | | 5 | **部署到开发环境**. 有一个可在其中进行标签迭代开发的环境。 | [将Analytics实施部署到开发环境](./deploy-dev.md) | | 6 | **验证并发布到生产环境**. 将标记属性添加到您的网站。 然后，使用数据元素、规则等自定义您的实施。| [验证开发实施并发布到生产环境](./validate-publish-prod.md) |

## 其他资源

标记可高度定制。详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)：了解界面的使用方式和可用的扩展。

- [实施变量](../vars/overview.md)：确定要发送到数据收集服务器的变量。
