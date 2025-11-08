---
title: 数据对象变量映射到Adobe Analytics
description: 查看Experience Platform Edge自动映射到Analytics变量的数据对象字段。
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 59d9dd8055a13046d05ac4c3b5261a6c5a919b5c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---

# 数据对象变量映射到Adobe Analytics

下表显示了Adobe Experience Platform Edge Network自动映射到Adobe Analytics的数据对象变量。 如果您使用这些数据对象字段路径，则无需额外配置即可将数据发送到Adobe Analytics。

如果您打算将来使用Customer Journey Analytics，建议使用这些字段。 这种实施方法允许贵组织使用Web SDK将数据发送到Adobe，而不遵循XDM架构。 当您的组织准备好将数据发送到Adobe Experience Platform时，您可以使用[数据流映射](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/data-prep#mapping)将数据对象字段指向它们各自的XDM字段。

## 价值优先级

此表的大多数数据对象字段与[映射的XDM字段](xdm-var-mapping.md)一致。 如果同时设置给定数据对象字段及其各自的XDM字段，则数据对象字段优先。 例如，如果字段`data.__adobe.analytics.events`存在，它将覆盖所有与事件相关的XDM对象字段。

某些数据对象字段还支持其各自的[查询参数值](../validate/query-parameters.md)作为简写值。 您可以交替使用标准数据对象字段和速记数据对象字段，只要它们分别用于唯一变量即可。 避免同时设置标准数据对象字段及其各自的简写数据对象字段。 Adobe无法保证哪个字段优先。

## 数据对象字段映射

以前对此表的更新可以在GitHub[上此页面的](https://github.com/AdobeDocs/analytics.zh-Hans/commits/main/help/implement/aep-edge/data-var-mapping.md)提交历史记录中找到。 与AppMeasurement变量类似，所有数据对象字段都区分大小写。

| 数据对象字段路径 | Analytics变量和描述 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | [浏览器高度](../../components/dimensions/browser-height.md)维度。 还支持简写字段`data.__adobe.analytics.bh`。 |
| `data.__adobe.analytics.browserWidth` | [浏览器宽度](../../components/dimensions/browser-width.md)维度。 还支持简写字段`data.__adobe.analytics.bw`。 |
| `data.__adobe.analytics.campaign` | [跟踪代码](../../components/dimensions/tracking-code.md)维度。 还支持简写字段`data.__adobe.analytics.v0`。 |
| `data.__adobe.analytics.channel` | [网站区域](../../components/dimensions/site-section.md)维度。 还支持简写字段`data.__adobe.analytics.ch`。 |
| `data.__adobe.analytics.colorDepth` | [颜色深度](../../components/dimensions/color-depth.md)维度。 还支持简写字段`data.__adobe.analytics.c`。 |
| `data.__adobe.analytics.connectionType` | [连接类型](../../components/dimensions/connection-type.md)维度。 还支持简写字段`data.__adobe.analytics.ct`。 |
| `data.__adobe.analytics.contextData` | [上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。 |
| `data.__adobe.analytics.cookiesEnabled` | [Cookie支持](../../components/dimensions/cookie-support.md)维度。 还支持简写字段`data.__adobe.analytics.k`。 |
| `data.__adobe.analytics.currencyCode` | [`currencyCode`](../vars/config-vars/currencycode.md)实现变量。 还支持简写字段`data.__adobe.analytics.cc`。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md)实现变量。 |
| `data.__adobe.analytics.eVar1` — `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md)维度。 还支持简写字段`data.__adobe.analytics.v1` - `data.__adobe.analytics.v250`。 |
| `data.__adobe.analytics.events` | [自定义事件](../../components/metrics/custom-events.md)。 设置此字段的格式类似于[`events`](../vars/page-vars/events/events-overview.md)实现变量。 |
| `data.__adobe.analytics.javaEnabled` | [Java已启用](../../components/dimensions/java-enabled.md)维度。 还支持简写字段`data.__adobe.analytics.v`。 |
| `data.__adobe.analytics.latitude` | 帮助设置[位置](../../components/dimensions/lifecycle-dimensions.md)移动生命周期维度。 还支持简写字段`data.__adobe.analytics.lat`。 |
| `data.__adobe.analytics.linkName` | [自定义链接](../../components/dimensions/custom-link.md)、[下载链接](../../components/dimensions/download-link.md)或[退出链接](../../components/dimensions/exit-link.md)维度，具体取决于`data.__adobe.analytics.linkType`中的值。 还支持简写字段`data.__adobe.analytics.pev2`。 |
| `data.__adobe.analytics.linkURL` | [`linkURL`](../vars/config-vars/linkurl.md)实现变量。 还支持简写字段`data.__adobe.analytics.pev1`。 |
| `data.__adobe.analytics.linkType` | 确定链接点击的类型。 有效值包括`o` （自定义链接）、`d` （下载链接）和`e` （退出链接）。 还支持简写字段`data.__adobe.analytics.pe`。 |
| `data.__adobe.analytics.list1` — `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md)实施变量。 还支持简写字段`data.__adobe.analytics.l1` - `data.__adobe.analytics.list3`。 |
| `data.__adobe.analytics.longitude` | 帮助设置[位置](../../components/dimensions/lifecycle-dimensions.md)移动生命周期维度。 还支持简写字段`data.__adobe.analytics.lon`。 |
| `data.__adobe.analytics.pageName` | [页面](/help/components/dimensions/page.md)维度。 |
| `data.__adobe.analytics.pageURL` | [页面URL](/help/components/dimensions/page-url.md)维度。 还支持简写字段`data.__adobe.analytics.g`。 |
| `data.__adobe.analytics.pageType` | [`pageType`](../vars/page-vars/pagetype.md)实现变量。 |
| `data.__adobe.analytics.prop1` — `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md)维度。 还支持简写字段`data.__adobe.analytics.c1` - `data.__adobe.analytics.c75`。 |
| `data.__adobe.analytics.purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md)实现变量。 |
| `data.__adobe.analytics.products` | [`products`](../vars/page-vars/products.md)实现变量，格式类似。 |
| `data.__adobe.analytics.referrer` | [推荐人](/help/components/dimensions/referrer.md)维度。 |
| `data.__adobe.analytics.resolution` | [监视器分辨率](../../components/dimensions/monitor-resolution.md)维度。 还支持简写字段`data.__adobe.analytics.s`。 |
| `data.__adobe.analytics.server` | [服务器](/help/components/dimensions/server.md)维度。 |
| `data.__adobe.analytics.transactionID` | [`transactionID`](../vars/page-vars/transactionid.md)实现变量。 还支持简写字段`data.__adobe.analytics.xact`。 |
| `data.__adobe.analytics.zip` | [邮政编码](../../components/dimensions/zip-code.md)维度。 |

{style="table-layout:auto"}
