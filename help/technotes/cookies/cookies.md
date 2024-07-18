---
title: Adobe Analytics 和浏览器 Cookie
description: 了解跟踪预防措施如何影响 Adobe Analytics 设置的第三方和第一方 Cookie。
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: ac9221bd7d9397ed0f085245663f1f0056f7d68f
workflow-type: tm+mt
source-wordcount: '1909'
ht-degree: 100%

---

# Adobe Analytics 和浏览器 Cookie

本文档说明主流浏览器的跟踪预防措施如何影响 Adobe Analytics 设置的第三方 Cookie 和第一方 Cookie。其中包括有关 Apple 的 Intelligent Tracking Prevention (ITP) 计划以及 Chrome 通过 SameSite 属性对第三方 Cookie 的限制。

## 浏览器如何限制 Cookie 的使用？

>[!NOTE]
>如果有个人 ID（如经过哈希处理的登录 ID）可用，则 [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html#cda?lang=zh-Hans) 和 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#comparing-cja-to-traditional-adobe-analytics?lang=zh-Hans) 可使用它在 Cookie 间拼合。

### 第三方 Cookie 限制

在第三方上下文中使用的 Cookie 已经广泛弃用。Firefox 和 Safari 分别在 2019 和 2020 年开始默认阻止第三方 Cookie。Chrome 宣布，其将在 2023 年的某个时候停止支持第三方 Cookie。在这样做的时候，第三方 Cookie 将直接不可用。

此外，Chrome 目前仅允许当第三方上下文中将“SameSite”属性设置为“None”并且已标记为安全时，才允许 Cookie 发挥作用，这意味着它们只能用在 HTTPS 上。更多信息在“[什么是 SameSite Cookie 属性以及它如何影响 Analytics？](#samesite-effect)”部分中提供

#### 哪些 Adobe 第三方 Cookie 受影响？

访客 ID 服务使用 &quot;[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans)&quot; Cookie 为访客在不同的客户域中提供永久性标识符。旧版 Analytics ID 服务 &quot;s_vi&quot; Cookie 被设置为第三方 Cookie，用于不使用自定义 CNAME 收集域的实施。

在阻止第三方 Cookie 的浏览器上，跨域跟踪不可用。

### 第一方 Cookie 限制 {#limitations-first-party-cookies}

仅在所有主流浏览器上允许第一方 Cookie。但是，Apple 通过 Intelligent Tracking Program (ITP)，限制 Adobe 设置的第一方 Cookie 的生命周期。这将影响 Safari 以及 iOS 和 iPadOS 上的所有浏览器。

Adobe 的第一方 Cookie 限制为 7 天过期，对于 Apple 认定来自跟踪器的点进为 24 小时过期。在 7 天过期的情况下，如果用户访问您的网站，然后在这七天内回访，则该 Cookie 的失效日期另外延长 7 天。但是，如果某个用户访问您的网站并在第 8 天回访，则会将其第二次访问视为新用户。

目前，ITP 策略仅适用于 Adobe 设置的所有第三方 Cookie，不论您使用的是访客 ID 服务还是旧版 Analytics ID (&quot;s_vi&quot; cookie)。过去，这些策略仅适用于客户端设置的 Cookie，而不是通过 CNAME 实施在服务器端设置的 Cookie。但是，在 2020 年 11 月，ITP 进行了更新，同样应用到 CNAME 实施。

#### 对 ITP 策略重大更改的时间表 {#ITP-timeline}

* 2019 年 2 月的 [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)：客户端 Cookie 限制为 7 天过期
* 2019 年 4 月的 [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)：对于广告点击，当引用域满足以下条件时，客户端 Cookie 限制为 24 小时过期：a) 涉及到跨站点跟踪，以及 b) 最终 URL 包含了查询字符串和/或片段标识符。
* 2020 年 11 月的 [CNAME 遮蔽和跳出跟踪防御](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/)：ITP 限制扩大到了 CNAME 实施。

ITP 策略经常发生改变。有关最新策略，请查看 Apple 的 [Webkit 中的跟踪预防](https://webkit.org/tracking-prevention)。

#### 哪些 Adobe 第一方 Cookie 受影响？

Adobe 设置的所有第一方 Cookie 以及相关的 JavaScript 库均受 ITP 策略影响：

* Adobe Experience Cloud 访客 ID (ECID) 服务库设置的[“AMCV”Cookie](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans)
* 使用 CNAME 配置了第一方数据收集时的 Analytics 旧版 [&quot;s_vi&quot; Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans)
* Analytics 旧版 [&quot;s_fid&quot; Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hans)，这是在无法设置 &quot;s_vi&quot; 时使用的后备 Cookie

#### ITP 对 Safari for Analytics 有什么影响？

ITP 限制的影响根据用户的行为差别非常大。只有使用受 ITP 影响的浏览器（例如 Safari）并在 7 天之后才回访的访客受影响。如果访客不使用 ITP 浏览器或者在 7 天之内回访，则不受影响。非常重要的是，您需要在 Analytics 中查看自己的数据来了解此限制影响的程度。有关如何衡量对您网站影响的提示，请参阅“[如何确定 Safari 更改是否影响我的业务？](#measure-itp-effect)”

如果这些限制确实会影响您的数据，您将看到：

1. 访客计数增加，回访访客由于 Cookie 过期被视为新访客。基于“访客”量度的任何量度（例如“每位访客的销售额”）也会受影响。
2. 对归因的更改。归因依赖于将转化事件与同一访问者之前的活动相关联。Cookie 过期后，后续事件将与新访客相关联。新访客的活动不能与前一访客的活动相关联。

>[!NOTE]
>
>ITP 技术目前不适用于移动应用程序中的嵌入式浏览器。

## 第三方 Cookie 和第一方 Cookie 有何区别？

### 第三方 Cookie

第三方 Cookie 并非由用户访问的网站创建。

虽然浏览器目前以同样方式处理所有第三方 Cookie 并进行存储，但第三方 Cookie 可能会有不同的行为方式。对于客户的 Analytics 第三方 Cookie 实施，浏览器存储 Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hans) ID 作为第三方 Cookie，但客户端仅对 Adobe 发出调用，而不会向未知的或可疑的第三方域发出调用。此 Cookie 提供跨域的持久性标识符并允许安全 (HTTPS) 内容。有关更多信息，请参阅 [Cookie 和 Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hans)。

在 Analytics 实施中，第三方 Cookie 用于跨域跟踪以及用于广告用例，包括重新定位广告。您可使用第三方 Cookie 在访客访问您拥有的不同域时标识访客，或者在并非您拥有的网站上向其显示广告时进行标识。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### 第一方 Cookie

第一方 Cookie 特定于域，由客户网站创建，在用户访问网站时存储在客户端浏览器中。所有浏览器通常接受第一方 Cookie，虽然 [Safari 限制了一些类型的第一方 Cookie 的失效期](#limitations-first-party-cookies)。

在 Analytics 实施中，第一方 Cookie 用于标识在您的网站上的用户，因此支持所有用户活动分析。您不需要第三方 Cookie 来了解在网站上的活动。

有关更多信息，请参阅[关于第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hans)。

![Cookie 比较](/help/technotes/assets/cookies2.png)

## 什么是 SameSite Cookie 属性以及它会如何影响 Analytics Cookie？ {#samesite-effect}

随着 2020 年 2 月 Chrome 80 浏览器的发布（以及后续版本的 Firefox 和 Edge 浏览器），SameSite Cookie 属性强制执行三个不同值的规范，这些值控制 Cookie 是否可以在第三方上下文中使用：

* `None`：此设置允许跨站点访问，并允许在第三方上下文中传递 Cookie。要指定此属性，您还必须指定 `Secure`，并且所有浏览器请求都必须遵循 HTTPS。例如，在设置 Cookie 时，需要按如下方式配对属性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正确标记，则 Cookie 对较新的浏览器不可用，因此被拒绝。

* `Lax`：允许为使用 *safe*（只读，例如 `GET`）HTTP 方法的顶级导航使用 same-site Cookie 发送跨站点请求。

* `Strict`：不会为任何第三方网站请求发送相同站点 Cookie。仅当 Cookie 的站点与 URL 栏中的站点匹配时，才会发送 Cookie。

这些浏览器版本中的默认行为是将没有指定 `SameSite` 属性的 Cookie 视为与 `SameSite=Lax` 相同。

### Analytics 如何管理 SameSite Cookie 属性？

对于使用访客 ID 服务的客户，默认情况下，设置了 Cookie 的 `SameSite=None` 和 `secure` 属性，这两个属性允许这些 Cookie 支持第三方用例。

对于使用 Analytics 旧版标识符（`s_vi` 和 `s_fid` Cookie）的客户，Cookie 还被设置为启用具有以下标准收藏集域的第三方用例：`adobedc.net`、`2o7.net` 和 `omtrdc.net`。对于使用 CNAME 实施的客户，Analytics 设置 `SameSite=Lax`。

>[!NOTE]
>
>如果您拥有多个域并使用相同的 CNAME 在所有域中进行数据收集，则在这些其他域中将 Cookie 视为第三方 Cookie。如果您使用的是旧版 Analytics 标识符，则可能需要将设置更新为 `SameSite=None`，以便这些 Cookie 可以在您的站点之间共享。有关详细信息，请参阅下一节中的[为多个域使用一个 CNAME 时更改 SameSite 值](#samesite-one-cname)。

对于 Google 在 `SameSite` 设置为 `None` 时标识为错误处理 Cookie 的浏览器，`SameSite` 将保留为不设置。

下表总结了 Analytics Cookie 的 SameSite 属性：

![Cookie 表](/help/technotes/assets/cookies1.png)

### 网站如何解决对 SameSite 属性的要求？

#### 使用 HTTPS 提供所有网站页面服务

确认您的 JavaScript 配置为对 Adobe 服务的所有调用使用 HTTPS。

如果您的网站使用 Experience Cloud 访客 ID 服务，则服务将第三方 HTTP 调用重定向到其 HTTPS 端点，这会增加延迟，但意味着您无需更改配置。

#### 为多个域使用一个 CNAME 时更改 SameSite 值 {#samesite-one-cname}

>[!NOTE]
>
>以下信息仅与不使用 Experience Cloud 访客 ID 服务的网站相关。

如果在与您网站相同的域中设置了一个 CNAME 实施，则 Cookie 在第一方上下文中创建，并且您无需进行更改。

但是，如果您拥有多个域并使用相同的 CNAME 在所有域中进行数据收集，则在这些其他域中将 Cookie 视为第三方 Cookie。对于 Chrome 80 和更高版本，它在这些其他域中不再可见。为了让行为在多个浏览器之间更为相似，Analytics 明确将此 Cookie 的 `SameSite` 值设置为 `Lax`。如果您在友好的第三方上下文中使用此 Cookie，则必须使用 `SameSite=None` 值设置 Cookie，这还意味着您必须始终使用 HTTPS。如果您尚未这么做，则联系 Adobe 客户关怀部门为您更改安全 CNAME 的 SameSite 值。

## 如何确定 Safari 更改是否影响我的业务？ {#measure-itp-effect}

Adobe 建议在更改数据收集之前，在自己的公司内部衡量更改的影响。您可以使用 Analysis Workspace 衡量 ITP 跟踪预防对您单独业务的影响：

* 从受 ITP 控制的浏览器衡量流量的百分比：

   1. 创建一个区段以查看有多少访客使用 ITP 平台。

      >[!NOTE]
      >
      >受 ITP 影响的特定浏览器取决于您是否使用 CNAME 实施。有关更多详细信息，请参阅“[对 ITP 策略重大更改的时间表](#ITP-timeline)”。

      ![ITP 访客的区段](/help/technotes/assets/itp-visitor-segment.png)

   2. 将区段应用到访客的数量以了解您的用户群中 Safari 的相对使用量。这让您可创建类似于下面的表：

      ![按 ITP 访客统计的访客百分比](/help/technotes/assets/visits-vs-safari-visits.png)

* 使用非 Safari 浏览器衡量未在 7 天内回访的访客百分比。如果您的非 Safari 访客在 7 天内重复回访，则 Safari 流量不会受到明显的影响。

   1. 为非 Safari 流量创建类似于下文的区段。

      ![7 天后回访访客的区段](/help/technotes/assets/visits-after-seven-days.png)

   2. 将区段应用到访客的数量以了解您的用户群中 Safari 的相对使用量。这让您可创建类似于下面的表：

      ![7 天后回访访客的百分比](/help/technotes/assets/percent-visits-after-seven-days.png)

### 报告期间调整数据的方法

如果您的业务受 ITP 跟踪预防的影响，则可以考虑在报告期间采取以下措施来调整数据。

* 创建区段以过滤出 ITP 用户。

  ![非 ITP 访客的区段](/help/technotes/assets/non-itp-visitor-segment.png)

* 创建计算量度以调整已知访客的虚增。

  ![用于调整访客虚增的计算量度](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[减轻浏览器 Cookie 限制影响的选项](cookieless.md)
>[Apple 的新应用程序跟踪透明度框架对 Adobe Analytics 的影响](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
