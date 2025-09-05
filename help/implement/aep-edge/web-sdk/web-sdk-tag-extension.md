---
title: 使用Web SDK标记扩展将数据发送到Adobe Analytics
description: 首先，干净地实施Adobe Experience Platform数据收集，使用XDM和Adobe Analytics ExperienceEvent字段组将数据发送到Adobe Analytics。
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 16%

---

# 使用Web SDK标记扩展将数据发送到Adobe Analytics

此实施路径涉及使用Adobe Experience Platform数据收集中的标记的全新Web SDK安装。 其他实施路径将在单独的页面上介绍：

* [Web SDK JavaScript库](web-sdk-javascript-library.md)：使用Web SDK JavaScript库(`alloy.js`)的全新Web SDK安装。 与Web SDK标记扩展方法（此页面）类似，不同之处在于，您自己管理实施，而不是使用标记UI。 它需要Adobe Analytics ExperienceEvent字段组，其中包括要包含在XDM架构中的典型Analytics变量。
* [Analytics扩展到Web SDK扩展](analytics-extension-to-web-sdk.md)：采用一种流畅、有条不紊的方法从Adobe Analytics标记扩展迁移到Web SDK标记扩展。 在您的组织准备好使用Adobe Experience Platform服务(例如Customer Journey Analytics)之前，此方法会抑制使用XDM的需求。 使用`data`对象而不是`xdm`对象将数据发送到Adobe。
* [AppMeasurement到Web SDK JavaScript库](appmeasurement-to-web-sdk.md)：一种流畅、系统地迁移到Web SDK的方法，只不过它不使用标记。 而是手动删除Adobe Analytics数据收集库(`AppMeasurement.js`)并将其替换为Web SDK JavaScript库(`alloy.js`)。

## 此实施路径的优缺点

使用Web SDK扩展将数据发送到Adobe Analytics既有优点，也有缺点。 仔细权衡每个选项，以确定哪种方法最适合您的组织。

| 优点 | 缺点 |
| --- | --- |
| <ul><li>**最直接的方法**：此实施路径最直接，通常是新Web SDK实施的推荐路径。 如果您无需担心当前的Adobe Analytics实施，请填充适用的Web SDK XDM字段。</li><li>**预定义架构**：如果您的组织不需要自己的架构，则只需使用面向Adobe Analytics的架构即可。 即使您改用Customer Journey Analytics，此概念仍然适用；prop和eVar的概念不适用于Customer Journey Analytics，但您可以继续使用prop和eVar作为简单的自定义维度。</li><li>**无需开发人员干预即可管理标记**：标记允许您管理您的实施，而无需要求开发人员对您的实施进行代码更改。 您的开发人员会安装标记加载器脚本，并且您可以完全控制数据收集的方式。</li></ul> | <ul><li>**使用特定架构锁定**：当您的组织迁移到Customer Journey Analytics时，您必须选择继续使用Adobe Analytics架构，或迁移到您自己组织的架构（这将是单独的数据集）。 如果您的组织在迁移到Customer Journey Analytics时既要避免Adobe Analytics架构，又要避免迁移到单独的数据集，Adobe建议使用以下两种方法之一：<ul><li>使用`data`对象： `data`对象允许您在不符合XDM架构的情况下将数据发送到Adobe Analytics。 创建组织的架构后，您可以使用数据流映射将`data`对象字段映射到XDM。 [Analytics to Web SDK扩展](analytics-extension-to-web-sdk.md)和[AppMeasurement to Web SDK JavaScript库](appmeasurement-to-web-sdk.md)都使用此`data`对象。</li><li>完全跳过Adobe Analytics：如果您正在实施Web SDK，则可以将该数据发送到Adobe Experience Platform中的数据集，以供在Customer Journey Analytics中使用。 您可以使用任何喜欢的架构；Adobe Analytics完全不参与此工作流，因此不需要Adobe Analytics ExperienceEvent字段组。 此方法产生的技术债务最少，但也将Adobe Analytics完全排除在外。</li></ul></ul> |

>[!IMPORTANT]
>
>此实施方法要求您使用为Adobe Analytics配置的架构。 如果您的组织计划将来在Customer Journey Analytics中使用您自己的架构，则使用Adobe Analytics架构可能会给数据管理员或架构师带来困惑。 减轻这一障碍有多种选择：
>
>* 您可以在CJA中使用Adobe Analytics架构。 请注意，CJA没有prop或eVar的概念；它们被视为任何其他架构字段。 另请注意，在CJA中使用Adobe Analytics架构可能会使其他平台服务(例如Adobe Journey Optimizer或Real-Time Customer Data Platform)更难使用。
>* 您可以使用数据对象，这与迁移工作流类似。 请注意，使用数据对象要求您将每个数据对象字段映射到XDM架构字段。
>* 您可以完全跳过Adobe Analytics实施，并使用您自己的架构将数据发送到Adobe Experience Platform。 从长远来看，这种方法非常理想，允许贵组织开始使用Customer Journey Analytics。

## 实施Web SDK标记扩展所需的步骤

实施任务的高级概述：

![如何使用Web SDK扩展工作流实施Adobe Analytics，如本节所述。](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您已<b>定义报告包</b>。</td>
<td><a href="/help/admin/tools/manage-rs/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构</b>。 为了标准化数据收集以在利用 Adobe Experience Platform 的应用程序中使用，Adobe 创建了开放且公开记录的标准，即体验数据模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>创建数据层</b>来管理您网站上的数据跟踪。</td>
<td><a href="../../prepare/data-layer.md">创建数据层</a></td>
</tr>

<tr>
<td>4</td>
<td><b>配置数据流</b>。 数据流表示实施 Adobe Experience Platform Web SDK 时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans">配置数据流<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>将 Adobe Analytics 服务</b>添加到您的数据流。 该服务控制是否以及如何将数据发送到Adobe Analytics，以及具体将数据发送到哪些报表包。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans#analytics">将 Adobe Analytics 服务添加到数据流</a></td>
</tr>

<tr>
<td>6</td>
<td><b>创建标记属性</b>。 属性是用于引用标记管理数据的总容器。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=zh-Hans#for-web">为 Web 创建或配置标签属性</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>在您的标记属性中安装和配置 Web SDK 扩展</b>。配置 Web SDK 扩展以将数据发送到在步骤 4 中配置的数据流。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=zh-Hans">Adobe Experience Platform Web SDK 扩展概述</a></td>
</tr>

<tr>
<td>8</td>
<td><b>迭代、验证并发布</b>到生产环境。 嵌入代码以将标记资产包含到网站页面。 然后使用数据元素、规则等来定制您的实施。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=zh-Hans#embed-code">嵌入代码</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hans">发布概述</a></td>
</tr>

</table>
