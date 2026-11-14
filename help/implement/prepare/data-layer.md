---
title: 创建数据层
description: 了解数据层如何支持您的Analytics实施、Adobe为何推荐Adobe客户端数据层，以及如何通过每种实施方法读取数据层值。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# 创建数据层

数据层是网站上的JavaScript结构，用于公开Analytics实施收集的数据，例如页面名称、产品详细信息和订单ID。 网站代码将写入数据层，并且实施会从中读取数据以设置Analytics变量。 由于您的实施不依赖于页面的HTML，因此您可以重新设计网站而不会中断数据收集。

## 先决条件

[创建解决方案设计文档](solution-design.md)：贵组织必须符合跟踪要求。 在联系组织中的开发团队之前，请确保您已准备好解决方案设计文档。 解决方案设计所需的数据将决定数据层包含的内容。

## 选择数据层规范 {#specifications}

对于新的或重构的实现，Adobe建议使用[Adobe客户端数据层](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/overview) (ACDL)。 ACDL是一个开源JavaScript库，它为您的站点提供了一种将数据和事件推送到全局`adobeDataLayer`阵列的标准方法。 标记、Web SDK和AppMeasurement都可以从中读取，并且Adobe Experience Manager核心组件可以自动填充该变量。

您的组织可以自由使用其他规范，例如[客户体验数字数据层](https://www.w3.org/2013/12/ceddl-201312.pdf) (CEDDL)（将数据存储在全局`digitalData`对象中）或自定义规范。 最重要的是贵组织需要符合一个规范，以满足其需求。

下表将ACDL与基于对象的数据层（如CEDDL）进行比较：

| | Adobe客户端数据层(`adobeDataLayer`) | 基于对象的数据层，如CEDDL (`digitalData`) |
| --- | --- | --- |
| 站点代码如何写入数据 | 推送对象： `adobeDataLayer.push({ page: { name: "Home" } })` | 设置属性： `digitalData.page.pageInfo.pageName = "Home"` |
| 您的实施如何读取值 | Adobe客户端数据层标记扩展中的`adobeDataLayer.getState("page.name")`或&#x200B;**数据层计算状态**&#x200B;数据元素 | 核心标记扩展中的`digitalData.page.pageInfo.pageName`或&#x200B;**JavaScript变量**&#x200B;数据元素 |
| 您的实施如何知道数据已准备就绪 | 站点代码推送事件（如`{ event: "page view" }`），并且您的实施侦听该事件。 此外，侦听器也会针对添加之前推送的事件运行。 | 在网站代码完成填充后（例如，使用直接调用规则），您的实施必须读取对象。 |

## 示例数据层 {#example}

ACDL不需要特定的数据结构。 围绕解决方案设计文档设计结构，并为写入或读取数据层的每个人记录该文档。 本指南中的示例使用以下结构。

加载页面时，网站代码推送页面数据和页面查看事件：

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

当访客完成购买时，网站代码会推送订单详细信息和购买事件：

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDL将每次推送合并到一个名为计算状态的对象，您的实施将读取该状态。 事件对象告知您的实施何时读取它。 查看[数据和计算状态](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state)和[事件](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events)。

## 工作流 {#workflow}

使用数据层实施 Adobe Analytics 时通常遵循以下步骤：

1. **与网站开发团队合作实施数据层**：网站开发团队主要负责确保数据层包含正确的值。 与您的网站开发团队一起审阅此页面，以确保各团队的期望是一致的。 请参阅[安装Adobe客户端数据层](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/install)。
1. **使用浏览器控制台验证数据层**：打开浏览器的开发人员控制台，在大多数浏览器中都可以使用`F12`键执行此操作。 运行`adobeDataLayer.getState()`以查看计算状态，或运行`adobeDataLayer.getState("page.name")`以查看单个值。 请参阅[验证安装](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/install#verify)。
1. **将数据层连接到Adobe Analytics**：此步骤因您组织的实施方法而异。 请参阅[将数据层连接到Adobe Analytics](#connect)。

## 将数据层连接到Adobe Analytics {#connect}

下表显示了每种实施方法如何从Adobe Client Data Layer读取：

| 实施方法 | 如何读取数据层 | 更多信息 |
| --- | --- | --- |
| Web SDK 标记扩展 | 通过Adobe客户端数据层扩展中的&#x200B;**数据层推送**&#x200B;事件触发规则。 将数据层值映射到XDM字段或通过Web SDK **更新变量**&#x200B;操作映射到`data`对象，然后通过&#x200B;**发送事件**&#x200B;操作发送它们。 | [使用Web SDK](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/web-sdk)、[XDM对象字段映射](../aep-edge/xdm-var-mapping.md)和[数据对象字段映射](../aep-edge/data-var-mapping.md)发送Adobe客户端数据层数据 |
| Web SDK JavaScript库 | 侦听具有`addEventListener()`的数据层事件，并在调用`sendEvent`时从数据层设置XDM或`data`字段。 | [使用Web SDK](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/web-sdk)、[XDM对象字段映射](../aep-edge/xdm-var-mapping.md)和[数据对象字段映射](../aep-edge/data-var-mapping.md)发送Adobe客户端数据层数据 |
| Analytics 扩展 | 使用&#x200B;**数据层推送**&#x200B;事件触发规则，并从Adobe客户端数据层扩展创建&#x200B;**数据层计算状态**&#x200B;数据元素。 在&#x200B;**设置变量**&#x200B;操作中将数据元素分配给Analytics变量，然后使用&#x200B;**发送信标**&#x200B;操作发送数据。 | [将数据层对象映射到数据元素](../launch/layer-to-elements.md)和[将数据元素映射到Analytics变量](../launch/elements-to-variable.md) |
| AppMeasurement | 在ACDL加载后读取带有`getState()`的值，然后调用`s.t()`。 | [使用AppMeasurement读取数据层](#appmeasurement) |

### 使用AppMeasurement读取数据层 {#appmeasurement}

加载库时，ACDL将其`getState()`方法添加到`adobeDataLayer`数组。 要确保库已加载并且计算状态包含最新数据，请读取事件侦听器中的值：

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

侦听器针对每个`page view`事件（包括在添加侦听器之前推送的事件）运行一次。 本指南中的变量页面（如[`pageName`](../vars/page-vars/pagename.md)）显示了如何使用`getState()`读取各个值。 在这样的侦听器中或&#x200B;**数据层推送**&#x200B;事件触发的Analytics扩展规则的自定义代码编辑器中使用这些示例。

如果您的实施每页发送多个点击，例如在单页应用程序中，请使用[`clearVars()`](../vars/functions/clearvars.md)，以便来自一次点击的值不会持续到下一次点击。

## 后续步骤

* [将数据层对象映射到数据元素](../launch/layer-to-elements.md)：在Adobe Experience Platform标记中使用网站的数据层。
* [Adobe客户端数据层文档](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/acdl/overview)：了解每个ACDL方法、事件和最佳实践。
