---
title: 使用Web SDK标记扩展将数据发送到Adobe Analytics
description: 首先，干净地实施Adobe Experience Platform数据收集，使用XDM和Adobe Analytics ExperienceEvent字段组将数据发送到Adobe Analytics。
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# 使用Web SDK标记扩展将数据发送到Adobe Analytics

此实施路径涉及使用Adobe Experience Platform数据收集中的标记的全新Web SDK安装。 其他实施路径将在单独的页面上介绍：

* [Web SDK JavaScript库](web-sdk-javascript-library.md)：使用Web SDK JavaScript库的全新Web SDK安装(`alloy.js`)。 与Web SDK标记扩展方法（此页面）类似，只是您自己管理实施，而不是使用标记UI。 它需要Adobe Analytics ExperienceEvent字段组，其中包括要包含在XDM架构中的典型Analytics变量。
* [Analytics到Web SDK的扩展](analytics-extension-to-web-sdk.md)：采用一种流畅、有条不紊的方法从Adobe Analytics标记扩展迁移到Web SDK标记扩展。 在您的组织准备好使用Adobe Experience Platform服务(如Customer Journey Analytics)之前，此方法会抑制使用XDM的需求。 使用 `data` 对象而不是 `xdm` 对象，将数据发送到Adobe。
* [Web SDK JavaScript库AppMeasurement](appmeasurement-to-web-sdk.md)：一种流畅、系统地迁移到Web SDK的方法，只不过它不使用标记。 您而是需要手动删除Adobe Analytics数据收集库(`AppMeasurement.js`)并将其替换为Web SDK JavaScript库(`alloy.js`)。

## 此实施路径的优缺点

使用Web SDK扩展将数据发送到Adobe Analytics既有优点，也有缺点。 仔细权衡每个选项，以确定哪种方法最适合您的组织。

| 优势 | 缺点 |
| --- | --- |
| <ul><li>**最直接的方法**：此实施路径最直接，通常是新Web SDK实施的推荐路径。 如果您无需担心当前的Adobe Analytics实施，请填充适用的Web SDK XDM字段。</li><li>**预定义架构**：如果您的组织不需要自己的架构，您只需使用面向Adobe Analytics的架构即可。 即使您转到Customer Journey Analytics，此概念仍然适用；prop和eVar的概念不适用于Customer Journey Analytics，但您可以继续使用prop和eVar作为简单的自定义维度。</li><li>**无需开发人员干预即可管理标记**：利用标记，您可以管理实施，而无需请求开发人员对您的实施进行代码更改。 您的开发人员会安装标记加载器脚本，并且您可以完全控制数据收集的方式。</li></ul> | <ul><li>**使用特定架构锁定到**：当您的组织迁移到Customer Journey Analytics时，您必须选择继续使用Adobe Analytics架构，或迁移到您自己的组织的架构（这将是单独的数据集）。 如果您的组织在迁移到Customer Journey Analytics时既要避免Adobe Analytics架构，又要避免迁移到单独的数据集，则Adobe建议使用以下两种方法之一：<ul><li>使用 `data` 对象： `data` 对象允许您在不符合XDM架构的情况下将数据发送到Adobe Analytics。 创建组织的架构后，便可以使用数据流映射进行映射 `data` 到XDM的对象字段。 两者都是 [Analytics到Web SDK的扩展](analytics-extension-to-web-sdk.md) 和 [Web SDK JavaScript库AppMeasurement](appmeasurement-to-web-sdk.md) 使用此 `data` 对象。</li><li>完全跳过Adobe Analytics：如果您正在实施Web SDK，则可以将该数据发送到Adobe Experience Platform中的数据集，以用于Customer Journey Analytics。 您可以使用任何喜欢的架构；Adobe Analytics完全不参与此工作流，因此不需要Adobe Analytics ExperienceEvent字段组。 此方法产生的技术债务最少，但也将Adobe Analytics完全排除在外。</li></ul></ul> |


