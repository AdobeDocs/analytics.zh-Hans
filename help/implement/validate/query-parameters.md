---
title: 数据收集查询参数
description: 列出了图像请求中使用的所有查询字符串参数。
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 725
ht-degree: 92%

---

# 数据收集查询参数

下表列出了 Adobe 在图像请求中使用的所有查询字符串参数。 在以下情况下可使用此信息：使用[数据包分析程序](packet-monitor.md)进行调试时、[对图像请求进行硬编码时](../other/hardcoded.md)，或者当使用[动态变量](../vars/page-vars/dynamic-variables.md)时。

| 参数 | Analytics 实施变量 | 描述 |
| --- | --- | --- |
| `aamlh` | 无 | Audience Manager位置提示。 用于Experience Cloud共享配置文件集成。 |
| `aamb` | 无 | Audience Manager blob. 用于Experience Cloud共享配置文件集成。 |
| `aid` | 无 | Analytics 访客 ID。 |
| `AQB` | 无 | 指示图像请求查询字符串的开头。 |
| `AQE` | 无 | 指示图像请求的结尾，这表明该请求未被截断。 |
| `bh` | 无 | 浏览器高度（像素）。 在[浏览器高度](/help/components/dimensions/browser-height.md)维度中使用。 |
| `bw` | 无 | 浏览器宽度（像素） 在[浏览器宽度](/help/components/dimensions/browser-width.md)维度中使用。 |
| `c` | 无 | 颜色质量（位） 在[颜色深度](/help/components/dimensions/color-depth.md)维度中使用。 |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | 指示上下文数据变量的开头。 从不包含值。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | 指示上下文数据变量的结尾。 从不包含值。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md) 或自定义流量变量。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | 点击中使用的货币类型。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | 域中的句点数。 用于帮助正确存储 Cookie。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | 图像请求的字符编码。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 访客 Cookie 的生命周期。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | 在[网站区域](/help/components/dimensions/site-section.md)维度中使用。 |
| `cp` | 无 | 在[点击类型](/help/components/dimensions/hit-type.md)维度中使用。 |
| `ct` | 无 | 在[连接类型](/help/components/dimensions/connection-type.md)维度中使用。 |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 指示要用作动态变量的参数。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events` 查询字符串的简写形式。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | 以逗号分隔的页面事件列表。 由大多数[量度](/help/components/metrics/overview.md)使用。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | 页面的当前 URL，最多 255 字节。 在[页面 URL](/help/components/dimensions/page-url.md) 维度中使用。 |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | 长度超过 255 字节的 URL 将被拆分。 前 255 个字节显示在 `g` 参数中，其余所有字节都显示在 `-g` 参数中。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName` 查询字符串的简写形式。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType` 查询字符串的简写形式。 |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | 表示[客户端提示](/help/technotes/client-hints.md)的几个变量的前缀。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | 层次结构维度。 |
| `hp` | 无 | 已不再使用。 在早期版本的 Adobe Analytics 中，用于确定当前 URL 是否是浏览器的主页。 |
| `j` | 无 | 浏览器中安装的 JavaScript 版本。 |
| `k` | 无 | 在 [Cookie 支持](/help/components/dimensions/cookie-support.md)维度中使用。 |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | 列表变量。 |
| `lrt` | 无 | “上次请求时间”，即上次请求的往返时间，以毫秒为单位。 仅当从一个页面发出多个请求或页面是单页面应用程序 (SPA) 时才发送。 |
| `mid` | 无 | Experience Cloud 访客 ID。 |
| `ndh` | 无 | 指示图像请求是否来自 AppMeasurement 的标记。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | 帮助确定 Cookie 的设置位置。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最后一页的对象标识符。 在 Activity Map 中使用。 |
| `ot` | 无 | 最后一页的对象名称。 在 Activity Map 早期版本中使用。 |
| `p` | 无 | 已不再使用。 浏览器中使用的插件的列表。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | 在[页面](/help/components/dimensions/page.md)维度中使用。 |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | 在[页面未找到](/help/components/dimensions/pages-not-found.md)维度中使用。 |
| `pccr` | 无 | 仅为新访客设置，并始终设置为 `true`。 如果访客拒绝 Cookie，有助于防止无限重定向。 |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | 确定自定义链接的类型。 [自定义链接](/help/components/dimensions/custom-link.md)、[下载链接](/help/components/dimensions/download-link.md)和[退出链接](/help/components/dimensions/exit-link.md)需要。 |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | 自定义链接的 URL。 |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | 自定义链接友好名称。 |
| `pev3` | 无 | 已不再使用。 在早期版本的视频报告中，用于跟踪里程碑。 |
| `pf` | 无 | 平台标志；仅供 Adobe 使用。 请勿更改。 |
| `pid` | 无 | 最后一页的页面标识符。 在 Activity Map 早期版本中使用。 |
| `pidt` | 无 | 最后一页的页面标识符类型。 在 Activity Map 早期版本中使用。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products` 查询字符串的简写形式。 |
| `products` | [`products`](../vars/page-vars/products.md) | 产品变量。 在[产品](/help/components/dimensions/product.md)和[类别](/help/components/dimensions/category.md)维度中使用。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | 用于去除重复购买。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | 点击的反向链接 URL。 在流量源维度中使用，例如[反向链接](/help/components/dimensions/referrer.md)和[反向链接域](/help/components/dimensions/referring-domain.md) |
| `s` | 无 | 屏幕分辨率（以 `width x height` 为单位）。 在[显示器分辨率](/help/components/dimensions/monitor-resolution.md)维度中使用。 |
| `server` | [`server`](../vars/page-vars/server.md) | [服务器](/help/components/dimensions/server.md)维度。 |
| `sv` | [`server`](../vars/page-vars/server.md) | `server` 查询字符串的简写形式。 |
| `state` | [`state`](../vars/page-vars/state.md) | “状态”维度。 |
| `t` | 无 | 点击的生成日期/时间。 在JavaScript中使用格式`dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss`为日期/时间。 `0`月是一月，而`11`月是十二月。<br>- `w`是一周中的某一天。 `0`是星期日，而`6`是星期六。<br>- `o`是以分钟为单位的负GMT偏移。 例如，`420` 表示 GMT-7。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | 为点击设置的自定义时间戳。 通常用于离线跟踪。 |
| `v` | 无 | 在[已启用 Java](/help/components/dimensions/java-enabled.md) 维度中使用。 |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [跟踪代码](/help/components/dimensions/tracking-code.md)维度。 |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) 或自定义转化维度。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 访客 ID 变量。 |
| `vidn` | 无 | 由 AppMeasurement 为新访客设置。 包含存储在访客 Cookie 中的 ID。 |
| `vmk` | `vmk` | 已不再使用。 访客迁移密钥，帮助将实施从第三方迁移到第一方 Cookie。 |
| `vvp` | `variableProvider` | 用于 Data Connectors。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | 与数据源结合使用，将在线和离线数据绑定在一起。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | 在[邮政编码](/help/components/dimensions/zip-code.md)维度中使用。 |
