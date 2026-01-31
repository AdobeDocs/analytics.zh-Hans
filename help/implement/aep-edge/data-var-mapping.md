---
title: 数据对象字段映射到Adobe Analytics
description: 查看 Experience Platform Edge 自动将哪些数据对象字段映射到 Analytics 变量。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 77%

---

# 数据对象字段映射到Adobe Analytics

下表显示了Adobe Experience Platform Edge Network自动映射到Adobe Analytics的数据对象字段。 如果使用这些数据对象字段路径，则无需额外配置即可将数据发送到 Adobe Analytics。

如果您打算将来使用 Customer Journey Analytics，建议使用这些字段。这种实施方法允许您的组织使用 Web SDK 将数据发送到 Adobe，无需遵循 XDM 架构。如果您的组织准备好将数据发送到 Adobe Experience Platform，您就可以使用[数据流映射](https://experienceleague.adobe.com/cn/docs/experience-platform/datastreams/data-prep#mapping)将数据对象字段指向它们各自的 XDM 字段。

## 值的优先级

此表中的大多数数据对象字段对应于[映射的XDM字段](xdm-var-mapping.md)。 在Adobe Analytics摄取期间，值首先从XDM映射到Analytics变量。 识别的数据对象字段映射到同一Analytics变量时，会映射并覆盖之前设置的任何值。 例如，如果存在`data.__adobe.analytics.events`，则它替换原本从XDM派生的整个事件集；事件不会跨两个源合并。 数据对象字段中的空字符串(`""`)将遮蔽其点击的映射Analytics变量，即使相应的XDM字段包含值也是如此。

某些数据对象字段还支持其相应的[查询参数值](../validate/query-parameters.md)作为简写值。您可以交替使用标准的数据对象字段和简写的数据对象字段，只要它们分别用于唯一的变量即可。应避免同时设置标准数据对象字段及其相应的简写数据对象字段。Adobe 无法保证哪个字段具有优先级。

## 数据对象字段映射

可以在此页面的 [GitHub 上的提交历史记录](https://github.com/AdobeDocs/analytics.zh-Hans/commits/main/help/implement/aep-edge/data-var-mapping.md)中找到此表之前的更新内容。与 AppMeasurement 变量类似，所有数据对象字段都区分大小写。

| 数据对象字段路径 | Analytics 变量和描述 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | [浏览器高度](../../components/dimensions/browser-height.md)维度。也支持简写字段 `data.__adobe.analytics.bh`。 |
| `data.__adobe.analytics.browserWidth` | [浏览器宽度](../../components/dimensions/browser-width.md)维度。也支持简写字段 `data.__adobe.analytics.bw`。 |
| `data.__adobe.analytics.campaign` | [跟踪代码](../../components/dimensions/tracking-code.md)维度。也支持简写字段 `data.__adobe.analytics.v0`。 |
| `data.__adobe.analytics.channel` | [网站分区](../../components/dimensions/site-section.md)维度。也支持简写字段 `data.__adobe.analytics.ch`。 |
| `data.__adobe.analytics.colorDepth` | [颜色深度](../../components/dimensions/color-depth.md)维度。也支持简写字段 `data.__adobe.analytics.c`。 |
| `data.__adobe.analytics.connectionType` | [连接类型](../../components/dimensions/connection-type.md)维度。也支持简写字段 `data.__adobe.analytics.ct`。 |
| `data.__adobe.analytics.contextData` | [&#x200B; 上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | [Cookie 支持](../../components/dimensions/cookie-support.md)维度。也支持简写字段 `data.__adobe.analytics.k`。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md) 实施变量。也支持简写字段 `data.__adobe.analytics.cc`。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 实施变量。 |
| `data.__adobe.analytics.eVar1` — `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) 维度。也支持简写字段 `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`。 |
| `data.__adobe.analytics.events` | [自定义事件](../../components/metrics/custom-events.md)。将此字段的格式设置为与 [`events`](../vars/page-vars/events/events-overview.md) 实施变量相似。 |
| `data.__adobe.analytics.javaEnabled` | [Java 已启用](../../components/dimensions/java-enabled.md)维度。也支持简写字段 `data.__adobe.analytics.v`。 |
| `data.__adobe.analytics.latitude` | 帮助设置[位置](../../components/dimensions/lifecycle-dimensions.md)移动生命周期维度。也支持简写字段 `data.__adobe.analytics.lat`。 |
| `data.__adobe.analytics.linkName` | [自定义链接](../../components/dimensions/custom-link.md)、[下载链接](../../components/dimensions/download-link.md)或者[退出链接](../../components/dimensions/exit-link.md)维度，取决于 `data.__adobe.analytics.linkType` 中的值。也支持简写字段 `data.__adobe.analytics.pev2`。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md) 实施变量。也支持简写字段 `data.__adobe.analytics.pev1`。 |
| `data.__adobe.analytics.linkType` | 确定所点击链接的类型。有效值包括`o`（自定义链接）、`d`（下载链接）和`e`（退出链接）。也支持简写字段 `data.__adobe.analytics.pe`。 |
| `data.__adobe.analytics.list1` — `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md)实施变量。也支持简写字段 `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`。 |
| `data.__adobe.analytics.longitude` | 帮助设置[位置](../../components/dimensions/lifecycle-dimensions.md)移动生命周期维度。也支持简写字段 `data.__adobe.analytics.lon`。 |
| `data.__adobe.analytics.pageName` | [页面](/help/components/dimensions/page.md)维度。 |
| `data.__adobe.analytics.pageURL` | [页面 URL](/help/components/dimensions/page-url.md) 维度。也支持简写字段 `data.__adobe.analytics.g`。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md) 实施变量。 |
| `data.__adobe.analytics.prop1` — `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) 维度。也支持简写字段 `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) 实施变量。 |
| `data.__adobe.analytics.products` | [`products`](../vars/page-vars/products.md) 实施变量，采用类似格式。 |
| `data.__adobe.analytics.referrer` | [反向链接](/help/components/dimensions/referrer.md)维度。 |
| `data.__adobe.analytics.resolution` | [显示器分辨率](../../components/dimensions/monitor-resolution.md)维度。也支持简写字段 `data.__adobe.analytics.s`。 |
| `data.__adobe.analytics.server` | [服务器](/help/components/dimensions/server.md)维度。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md) 实施变量。也支持简写字段 `data.__adobe.analytics.xact`。 |
| `data.__adobe.analytics.zip` | [邮政编码](../../components/dimensions/zip-code.md)维度。 |

{style="table-layout:auto"}
