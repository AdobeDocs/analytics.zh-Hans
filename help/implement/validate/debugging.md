---
title: 调试Analytics数据收集
description: 确认Adobe Analytics从AppMeasurement、Analytics扩展、Web SDK、Mobile SDK和数据插入API接收您所需的数据。
keywords: 调试，验证，数据包分析程序，数据包监视器， /b/ss/， Edge跟踪， Assurance， hitdebugger，报表包
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# 调试Analytics数据收集

本文介绍了在调试发送到Adobe Analytics的数据时应检查的内容。 在下表中找到您的实施方法，并关注其部分。 如果您正在调查意外的报告数据，请从[将请求与报告进行比较](#reports)开始。

有关适用于所有Adobe数据收集的步骤和工具，如捕获网络请求、启用调试日志记录和调查已取消的请求，请参阅[调试和解决数据收集问题](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview)。

| 实施方法 | 在何处查看Analytics接收的数据 | 指引 |
| --- | --- | --- |
| AppMeasurement或Analytics标记扩展 | 从浏览器直接向Analytics数据收集服务器发出的请求 | [AppMeasurement](#appmeasurement) |
| Web SDK | Edge跟踪，在Edge Network将您的事件转换为Analytics点击后 | [Web SDK](#web-sdk) |
| Mobile SDK | Assurance中的“Analytics事件”视图。 如果您使用Edge Network或Edge Bridge扩展，请打开&#x200B;**[!UICONTROL Analytics Edge视图]**。 | Assurance中的[Adobe Analytics事件视图](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/assurance/view/adobe-analytics) |
| 数据插入 API | 服务器的传出请求及其响应 | [数据插入API请求疑难解答](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement和Analytics扩展 {#appmeasurement}

### 查找请求 {#appmeasurement-find}

[捕获网络请求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web)并筛选`/b/ss/`。 标记调试器（如Adobe Experience Platform Debugger）会为您标识和解码这些请求。

如果未显示`/b/ss/`请求：

* 检查浏览器控制台中是否存在JavaScript错误。
* 如果您使用Analytics标记扩展，请确认标记嵌入代码位于页面的`<head>`元素中，并且您的库已发布到要测试的环境。 [标记调试模式](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging)显示发送点击的规则是否触发。
* 如果您自行托管AppMeasurement，请直接打开库的URL，以确认文件已加载并包含代码。
* 禁用浏览器扩展（如广告拦截器），这些扩展可能会阻止发送请求。
* Debugger无法识别从iframe中发送的请求。 请改用浏览器开发人员工具。 请参阅[将AppMeasurement与iFrame结合使用](../use-cases/iframe.md)。

### 检查Analytics接收的内容 {#appmeasurement-contents}

* **报表包**： `/b/ss/`之后的路径区段列出了接收点击的报表包ID。 确认它们就是您期望的报表包，例如开发页面上的开发报表包。
* **变量**：原始请求使用查询参数名称而不是变量名称；例如，eVar1显示为`v1`，prop1显示为`c1`。 请参阅[变量引用](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)。 当请求太长时，AppMeasurement会使用HTTP `POST`发送该请求，这样请求正文中就会显示变量，而不是URL。
* **点击类型**： [`tl()`](../vars/functions/tl-method.md)发送的请求包含`pe`参数，并且不增加页面查看次数。 由[`t()`](../vars/functions/t-method.md)发送的请求不包括`pe`。

如果值存在但错误，请参阅[JavaScript实施疑难解答](../js/troubleshooting.md)以了解常见原因，例如引号、大写和空格。

### 检查响应 {#appmeasurement-response}

`2xx`响应仅确认数据收集服务器已收到请求，而不确认点击已记录。 使用默认响应类型时，即使丢弃点击，请求也可以返回成功。 新访客的第一个请求应该有`302`响应。 请参阅[HTTP响应代码](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)。

AppMeasurement通过`navigator.sendBeacon()`发送退出链接请求以及启用[`useBeacon`](../vars/config-vars/usebeacon.md)时发送的所有请求。 开发人员工具可以将这些请求标记为已取消，即使浏览器发送了这些请求也是如此。 查看[已中止的请求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests)。

## Web SDK {#web-sdk}

### 查找请求 {#web-sdk-find}

使用Web SDK时，浏览器将事件发送到Edge Network，而不是直接发送到Analytics，因此您不会看到`/b/ss/`请求。 [检查Edge Network请求](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests)并确认以下内容：

* `configId`参数与您启用了[Adobe Analytics服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure#analytics)的数据流匹配，并包含您期望的报表包。
* 有效负载符合页面查看或链接事件的条件。 Analytics会忽略不包含页面详细信息或Web交互类型的负载。 查看Adobe Analytics中的[Edge Network事件类型](../aep-edge/hit-types.md)。

### 检查Analytics接收的内容 {#web-sdk-contents}

启动[Edge跟踪](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace)并重现操作。 找到以&#x200B;**[!UICONTROL Analytics自动映射]**&#x200B;开头的行，然后展开`mappedQueryParams`及其下的报表包ID。

* **变量**：映射的值使用与AppMeasurement请求相同的查询参数名称，有时使用简写形式，例如`gn`表示页面名称，`pl`表示产品。 查看[XDM对象字段映射](../aep-edge/xdm-var-mapping.md)和[数据对象字段映射](../aep-edge/data-var-mapping.md)。
* **上下文数据**：未映射到Analytics变量的XDM字段显示为前缀为`c.a.x.`的上下文数据。 使用[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)将它们分配给变量。
* **报表包**：如果您使用报表包覆盖，则Edge跟踪中的数据流配置行会显示Edge Network使用的报表包。

### 支票处理 {#web-sdk-processing}

在Edge跟踪打开的Assurance会话中，搜索`hitdebugger`的事件。 这些事件使用供应商`com.adobe.analytics.hitdebugger`，并且其负载在Analytics处理后显示值，例如Experience Cloud ID (`mcvisId`)和`pageName`。

有关引导式演练，请参阅[使用Adobe Experience Platform Web SDK设置Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics)。

## 将请求与报表进行比较 {#reports}

到达Analytics的点击不会立即出现在报表中，并且报告的值可能与请求中的值不同：

* **延迟**：收集后大约两小时，报表中通常会显示完整数据。 某些数据（例如带有时间戳的点击）可能需要更长的时间。 查看[数据可用性和延迟](/help/technotes/latency.md)。
* **正在处理**：处理规则、VISTA规则、机器人规则和其他处理步骤可以在收集后更改或排除值。 查看Adobe Analytics[&#128279;](/help/technotes/processing-order.md)中数据的处理顺序。 Assurance后处理数据显示单个点击的处理结果。
* **报表包**：确认您查看的报表包与请求或数据流针对的报表包相同。
* **意外值**：如果维度显示意外峰值或值，请参阅[哈希冲突](hash-collisions.md)。

有关更广泛的流量更改，请参阅[数据激增和骤减故障诊断](/help/technotes/event/spikes-drops.md)。
