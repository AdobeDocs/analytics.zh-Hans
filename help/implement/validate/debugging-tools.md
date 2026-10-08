---
title: Analytics实施的调试工具
description: 使用Analytics调试器、浏览器开发人员工具和HTTP调试代理检查您的实施发送到Adobe的数据。
keywords: 数据包分析程序、数据包监视器、数据包探查程序、调试程序、charles、NS_BINDING_ABORTED、sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Analytics实施的调试工具

调试工具（有时称为数据包分析程序或数据包探查程序）允许您检查实施发送至Adobe的数据。 它们可以帮助您确认请求是否成功触发，检查这些请求中包含的变量和负载，以及排查意外的实施行为。

>[!NOTE]
>
>此页面上列出的工具不完整。 它们代表Adobe Analytics客户认为有用的工具。 除了Adobe提供的工具外，Adobe不支持这些产品，也不对这些产品进行故障诊断。 有关安装、使用和支持信息，请咨询工具的发布者。

## 选择调试工具

以下类别可帮助您根据要检查的内容选择工具。

| 工具类型 | 在以下情况下很有用 |
| --- | --- |
| **Analytics和标记调试器** | 您希望以易于用户识别的格式解释和呈现Analytics变量、标记、数据层或收集请求。 |
| **浏览器开发人员工具** | 您正在调试Web实施，并且希望直接检查网络请求，而无需安装单独的调试应用程序。 |
| **HTTP(S)调试代理** | 您希望检查来自浏览器、移动应用程序、WebViews、API或其他客户端的HTTP流量，或需要浏览器开发人员工具以外的功能。 |

## Analytics和标记调试器

Analytics和标记调试器可识别Analytics技术并解释其请求。 这些工具可以更轻松地识别Adobe Analytics变量、Experience Platform Web SDK负载、标记和相关实施信息，而无需手动解码网络请求。

| 工具 | 可用性 | 对以下项目很有用 | 注意事项 |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/debugger/home)** | 浏览器扩展 | 调试Adobe Experience Platform和CX Enterprise实施，包括Adobe Analytics、标记、数据层和Experience Platform Web SDK | Adobe提供的重点介绍Adobe技术的工具 |
| **[Omnibug](https://omnibug.io)** | 基于Chromium的浏览器和Firefox | 解码Adobe Analytics、Experience Platform Web SDK、Adobe标记以及来自许多其他分析和营销供应商的请求 | 对于包含来自多个供应商的技术实施非常有用 |
| **[ObservePoint调试器](https://www.observepoint.com/solutions/observepoint-debugger/)** | Chrome和Edge | 检查和解码分析、营销和测量标记，包括Adobe Analytics请求 | 基于浏览器的调试器；ObservePoint还提供了单独的自动化实施验证产品 |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/assurance/home)** | CX Enterprise中的Web应用程序 | 检查和验证Mobile SDK实施中的事件，并查看Edge Network如何处理事件 | Adobe提供的工具；将您的应用程序连接到Assurance会话以查看其事件 |

## 浏览器开发人员工具

每个现代浏览器都包含可检查网络请求的开发人员工具，因此您通常不需要单独的工具来调试Web实施。 按&#x200B;**F12**&#x200B;或&#x200B;**Ctrl+Shift+I**（Windows和Linux）或&#x200B;**Cmd+Option+I**(macOS)，然后选择&#x200B;**网络**&#x200B;选项卡。 在Safari中，首先在Safari的&#x200B;**高级**&#x200B;设置中启用开发人员功能。

## HTTP(S)调试代理

HTTP调试代理截获客户端和服务器之间的HTTP和HTTPS流量。 当浏览器开发人员工具提供的可见性不足，或者实施在传统Web浏览器之外运行时，这些变量将非常有用。

HTTPS检查通常需要将客户端配置为信任由调试代理提供的证书。 安装证书或截获加密通信时，请遵循贵组织的安全策略。

| 工具 | 对以下项目很有用 |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | 检查浏览器、应用程序、移动设备和其他HTTP流量 |
| **[随处都是Fiddler](https://www.telerik.com/fiddler/fiddler-everywhere)** | 捕获和检查应用程序和设备之间的HTTP(S)流量。 与旧版Fiddler Classic产品不同。 |
| **[Proxyman](https://proxyman.com/)** | 检查和修改来自浏览器、应用程序和移动设备的HTTP(S)流量 |
| **[HTTP工具包](https://httptoolkit.com/)** | 使用面向应用程序和API调试的工作流，检查来自应用程序、API、开发环境和移动设备的流量 |
| **[mitmproxy](https://www.mitmproxy.org/)** | 通过命令行和Web接口执行可脚本化的HTTP(S)拦截、检查和修改。 最适合习惯使用命令行工作流的用户。 |

## 找到Adobe Analytics请求

对于将数据直接发送到Adobe Analytics的实施（如AppMeasurement），请过滤网络请求：

```text
/ss/
```

Adobe Analytics收集请求在请求URL或有效负载中包含Analytics变量。 原始请求使用查询参数名称而不是变量名称；例如，eVar1显示为`v1`，prop1显示为`c1`。 Analytics调试器会为您解码这些名称。 要自行解码，请参阅数据插入API文档中的[变量引用](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference)。

有关Analytics数据收集服务器返回的HTTP状态代码，请参阅数据插入API文档中的[HTTP响应代码](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes)。

对于使用Adobe Experience Platform Web SDK的实施，过滤网络请求：

```text
/ee/
```

选择请求并检查其有效负载以查看发送到Adobe Experience Platform Edge Network的数据。 Web SDK会将数据发送到Edge Network，然后，可以将数据转发到Adobe Analytics和其他配置的服务。 检查客户端请求会验证浏览器发送到Edge Network的内容；它本身不会确认每个下游服务是否已成功处理数据。 要查看Edge Network如何处理事件，请使用[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/assurance/home)。

## 已中止的请求

当页面导航离开时，浏览器可以取消仍在进行的请求。 Firefox为这些请求添加标签`NS_BINDING_ABORTED`；Chrome和Edge为它们添加标签`(canceled)`。 若要在导航后保持请求可见，请启用&#x200B;**保留日志** （Chrome和Edge）或&#x200B;**保留日志** (Firefox)。

取消的请求并不一定意味着数据丢失。 浏览器可能已发送完整请求，并且仅停止等待响应。 浏览器开发工具通常无法显示差异，但HTTP调试代理可以。

与`navigator.sendBeacon()`一起发送的请求在导航时未取消。 AppMeasurement使用`sendBeacon`作为退出链接以及启用[`useBeacon`](/help/implement/vars/config-vars/usebeacon.md)时使用。 Web SDK将其用于与[`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading)一起发送的事件。 如果经常取消链接跟踪请求，请使用这些选项。
