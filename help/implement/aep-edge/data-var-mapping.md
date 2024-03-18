---
title: 数据对象变量映射到Adobe Analytics
description: 查看Edge自动映射到Analytics变量的数据对象字段。
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 5%

---

# 数据对象变量映射到Adobe Analytics

下表显示了Adobe Experience Platform Edge Network自动映射到Adobe Analytics的数据对象变量。 如果您使用这些数据对象字段路径，则无需额外配置即可将数据发送到Adobe Analytics。

如果您打算在将来使用Customer Journey Analytics，建议使用这些字段。 这种实施方法允许贵组织使用Web SDK向Adobe发送数据，而不遵循XDM架构。 当您的组织准备好将数据发送到Adobe Experience Platform时，您可以使用 [数据流映射](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) 将数据对象字段指向它们各自的XDM字段。

## 价值优先级

此表格中的大多数数据对象字段与 [映射的XDM字段](xdm-var-mapping.md). 如果您将两个 `data` 对象字段及其各自的XDM字段，数据对象字段优先。 如果同时使用XDM对象字段和数据对象字段，Adobe建议使用数据对象字段设置自定义事件。 如果字段 `data.__adobe.analytics.events` 存在，它会覆盖与商务和自定义事件相关的所有XDM对象字段。

某些数据对象字段也支持其各自对应的 [查询参数值](../validate/query-parameters.md) 作为速记值。 您可以交替使用标准数据对象字段和速记数据对象字段，只要它们分别用于唯一变量即可。 避免同时设置标准数据对象字段及其各自的简写数据对象字段。 Adobe无法保证哪个字段优先。

## 数据对象字段映射

可以在此页面的 [GitHub 上的提交历史记录](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md)中找到此表之前的更新内容。

| 数据对象字段路径 | Analytics变量和描述 |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | 此 [浏览器高度](../../components/dimensions/browser-height.md) 维度。 速记字段 `data.__adobe.analytics.bh` 也受支持。 |
| `data.__adobe.analytics.browserWidth` | 此 [浏览器宽度](../../components/dimensions/browser-width.md) 维度。 速记字段 `data.__adobe.analytics.bw` 也受支持。 |
| `data.__adobe.analytics.campaign` | 此 [跟踪代码](../../components/dimensions/tracking-code.md) 维度。 速记字段 `data.__adobe.analytics.v0` 也受支持。 |
| `data.__adobe.analytics.channel` | 此 [网站区域](../../components/dimensions/site-section.md) 维度。 速记字段 `data.__adobe.analytics.ch` 也受支持。 |
| `data.__adobe.analytics.colorDepth` | 此 [颜色深度](../../components/dimensions/color-depth.md) 维度。 速记字段 `data.__adobe.analytics.c` 也受支持。 |
| `data.__adobe.analytics.connectionType` | 此 [连接类型](../../components/dimensions/connection-type.md) 维度。 速记字段 `data.__adobe.analytics.ct` 也受支持。 |
| `data.__adobe.analytics.contextData` | [上下文数据变量](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | 此 [Cookie支持](../../components/dimensions/cookie-support.md) 维度。 速记字段 `data.__adobe.analytics.k` 也受支持。 |
| `data.__adobe.analytics.currencyCode` | 此 [`currencyCode`](../vars/config-vars/currencycode.md) 实施变量。 速记字段 `data.__adobe.analytics.cc` 也受支持。 |
| `data.__adobe.analytics.dynamicVariablePrefix` | 此 [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) 实施变量。 |
| `data.__adobe.analytics.eVar1` — `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) 维度。 速记字段 `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` 也受支持。 |
| `data.__adobe.analytics.events` | [自定义事件](../../components/metrics/custom-events.md). 设置此字段的格式类似于 [`events`](../vars/page-vars/events/events-overview.md) 实施变量。 |
| `data.__adobe.analytics.javaEnabled` | 此 [已启用Java](../../components/dimensions/java-enabled.md) 维度。 速记字段 `data.__adobe.analytics.v` 也受支持。 |
| `data.__adobe.analytics.latitude` | 帮助设置 [位置](../../components/dimensions/lifecycle-dimensions.md) 移动生命周期维度。 速记字段 `data.__adobe.analytics.lat` 也受支持。 |
| `data.__adobe.analytics.linkName` | 此 [自定义链接](../../components/dimensions/custom-link.md)， [下载链接](../../components/dimensions/download-link.md)，或 [退出链接](../../components/dimensions/exit-link.md) 维度，具体取决于中的值 `data.__adobe.analytics.linkType`. 速记字段 `data.__adobe.analytics.pev2` 也受支持。 |
| `data.__adobe.analytics.linkURL` | 此 [`linkURL`](../vars/config-vars/linkurl.md) 实施变量。 速记字段 `data.__adobe.analytics.pev1` 也受支持。 |
| `data.__adobe.analytics.linkType` | 确定链接点击的类型。 有效值包括 `o` （自定义链接）、 `d` （下载链接），以及 `e` （退出链接）。 速记字段 `data.__adobe.analytics.pe` 也受支持。 |
| `data.__adobe.analytics.list1` — `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) 实施变量。 速记字段 `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` 也受支持。 |
| `data.__adobe.analytics.longitude` | 帮助设置 [位置](../../components/dimensions/lifecycle-dimensions.md) 移动生命周期维度。 速记字段 `data.__adobe.analytics.lon` 也受支持。 |
| `data.__adobe.analytics.pageName` | [页面](/help/components/dimensions/page.md)维度。 |
| `data.__adobe.analytics.pageURL` | 此 [页面URL](/help/components/dimensions/page-url.md) 维度。 速记字段 `data.__adobe.analytics.g` 也受支持。 |
| `data.__adobe.analytics.pageType` | 此 [`pageType`](../vars/page-vars/pagetype.md) 实施变量。 |
| `data.__adobe.analytics.prop1` — `data.__adobe.analytics.prop75` | [属性](../../components/dimensions/prop.md) 维度。 速记字段 `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` 也受支持。 |
| `data.__adobe.analytics.purchaseID` | 此 [`purchaseID`](../vars/page-vars/purchaseid.md) 实施变量。 |
| `data.__adobe.analytics.products` | 此 [`products`](../vars/page-vars/products.md) 实施变量，格式与此类似。 |
| `data.__adobe.analytics.referrer` | [推荐人](/help/components/dimensions/referrer.md)维度。 |
| `data.__adobe.analytics.resolution` | 此 [监视器分辨率](../../components/dimensions/monitor-resolution.md) 维度。 速记字段 `data.__adobe.analytics.s` 也受支持。 |
| `data.__adobe.analytics.server` | [服务器](/help/components/dimensions/server.md)维度。 |
| `data.__adobe.analytics.tnta` | 用于A4T集成。 |
| `data.__adobe.analytics.transactionID` | 此 [`transactionID`](../vars/page-vars/transactionid.md) 实施变量。 速记字段 `data.__adobe.analytics.xact` 也受支持。 |
| `data.__adobe.analytics.zip` | 此 [邮政编码](../../components/dimensions/zip-code.md) 维度。 |

{style="table-layout:auto"}
