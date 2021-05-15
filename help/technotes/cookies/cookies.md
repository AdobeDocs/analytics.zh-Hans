---
title: Adobe Analytics 和浏览器 Cookie
description: 了解跟踪预防措施如何影响由Adobe Analytics设置的第三方和第一方cookie。
source-git-commit: b2f606e74aa0d2ab0f01ab7cbfc795bfd7cda461
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 7%

---


# Adobe Analytics 和浏览器 Cookie

本文档说明主要浏览器的跟踪预防措施如何影响由Adobe Analytics设置的第三方和第一方cookie。 它包含有关Apple的Intelligent Tracking Prevention(ITP)项目的信息，以及Chrome对通过SameSite属性访问第三方Cookie的限制。

## 浏览器如何限制Cookie的使用？

>[!NOTE]
>[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda)和[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics)可使用人员ID（如散列登录ID）在Cookie上串接。

### 第三方Cookie限制

在第三方上下文中使用的Cookie正被广泛弃用。 从2019年和2020年开始，Firefox和Safari在默认情况下开始阻止第三方Cookie。 Chrome已宣布计划在2022年某个时候停止支持第三方Cookie。 当他们这样做时，第三方Cookie实际上将无法使用。

此外，Chrome目前仅允许Cookie在第三方上下文中工作（如果它们的“SameSite”属性设置为“无”且标记为安全），即它们只能通过HTTPS使用。 “[什么是SameSite Cookie属性，以及它如何影响Analytics?](#samesite-effect)”部分提供了更多信息

#### 哪些Adobe第三方Cookie受影响？

访客ID服务使用“[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)”Cookie为不同客户域中的访客提供永久标识符。 旧版Analytics ID服务“s_vi”Cookie被设置为第三方Cookie，用于未使用自定义CNAME收集域的实施。

在阻止第三方Cookie的浏览器上，不提供跨域跟踪。

### 第一方Cookie限制{#limitations-first-party-cookies}

所有主要浏览器均允许使用第一方Cookie。 但是，Apple通过其智能跟踪项目(ITP)限制了由Adobe设置的第一方Cookie的使用期。 这会影响Safari以及iOS和iPadOS上的所有浏览器。

Adobe的第一方cookie仅限7天的过期时间，或者，对于苹果确定来自跟踪器的点击次数，限于24小时的过期时间。 如果用户在7天内访问您的网站并在7天内返回，则Cookie的过期日期将再延长7天。 但是，如果用户访问您的网站并在八天后返回，则在第二次访问时，他们将被视为新用户。

目前，ITP策略适用于由Adobe设置的所有第一方Cookie，无论您使用的是访客ID服务还是旧版Analytics ID(“s_vi”Cookie)。 这些策略一度仅应用于cookies设置客户端，而不应用于cookies通过CNAME实施设置服务器端。 但是，2020年11月更新了ITP，以同样适用于CNAME实施。

#### ITP策略{#ITP-timeline}的重大更改时间表

* 2019年2月，ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/):客户端Cookie的有效期限为七天[
* 2019年4月，ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/):当引用域a)参与跨站点跟踪和b)最终URL包含查询字符串和/或片段标识符时，客户端Cookie仅限24小时进行广告点击。[
* 2020年11月，带有[CNAME遮盖和弹回跟踪防御](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/):ITP限制已扩展到CNAME实施。

ITP政策在不断演变。 有关最新策略，请参阅Apple的[Webkit](https://webkit.org/tracking-prevention)中的跟踪预防。

#### 哪些Adobe第一方Cookie受影响？

由Adobe设置的所有第一方Cookie以及相关的JavaScript库都受ITP策略影响：

* [“AMCV”](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 由Adobe Experience Cloud访客ID(ECID)服务库设置
* 当Analytics旧版[&quot;s_vi&quot; cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)配置为使用CNAME进行第一方数据收集时
* Analytics旧版[&quot;s_fid&quot; cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)，它是无法设置&quot;s_vi&quot;时使用的回退Cookie

#### ITP对Safari for Analytics有何影响？

ITP限制的影响可能会因用户行为而显着不同。 只有使用受ITP影响的浏览器（例如Safari）并在七天缺勤后返回的访客受影响。 如果访客不使用ITP浏览器或在七天内返回，则不受影响。 在Analytics中查看您自己的数据，以了解此限制的影响程度非常重要。 有关如何衡量对您网站的影响的提示，请参阅“[如何确定Safari更改是否影响我的业务？](#measure-itp-effect)”

如果这些限制确实影响您的数据，您将看到：

1. 增加的访客计为退回访客，由于其Cookie已过期，因此会将其视为新访客。 任何基于访客量度的量度(如每个访客的销售量)也会受到影响。
2. 对归因的更改。 归因依赖于将转化事件与前一活动关联在一起的访客。 一旦Cookie过期，后续事件将与新访客关联。 新访客的活动不能与上一访客的活动绑定。

>[!NOTE]
>
>ITP技术目前不适用于移动应用程序中的嵌入式浏览器。

## 第三方 Cookie 和第一方 Cookie 有何区别？

### 第三方 Cookie

第三方Cookie不是由用户访问的网站创建的。

虽然浏览器当前对所有第三方Cookie的处理方式相同并存储它们，但第三方Cookie的行为方式可能不同。 通过客户的Analytics第三方Cookie实施，浏览器将Adobe[demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID存储为第三方Cookie，但客户端仅对Adobe进行调用，而不会对未知或可疑的第三方域进行调用。 此Cookie跨域提供永久标识符并允许安全(HTTPS)内容。 有关更多信息，请参阅 [Cookie 和 Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)。

在Analytics实施中，第三方Cookie用于跨域跟踪和广告使用案例，包括重定向广告。 第三方Cookie允许您在访客访问您拥有的不同域时或在您不拥有的网站上显示广告时识别其身份。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### 第一方 Cookie

第一方Cookie是特定于域的，由客户网站创建，并在用户访问网站时存储在客户端浏览器中。 所有浏览器一般都接受第一方Cookie，但[Safari限制某些类型的第一方Cookie的到期。](#limitations-first-party-cookies)

在Analytics实施中，第一方Cookie用于识别用户在您的网站上的时间，因此支持所有用户活动分析。 您不需要第三方Cookie即可了解现场活动。

有关更多信息，请参阅[关于第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)。

![Cookie 比较](/help/technotes/assets/cookies2.png)

## 什么是SameSite Cookie属性，它如何影响Analytics Cookie?{#samesite-effect}

随着2020年2月发布的Chrome 80浏览器以及Firefox和Edge浏览器的后续版本，SameSite cookie属性对三个不同值强制实施该规范，这些值控制Cookie是否可在第三方上下文中使用：

* `None`：此设置允许跨站点访问，并允许在第三方上下文中传递 Cookie。要指定此属性，您还必须指定 `Secure`，并且所有浏览器请求都必须遵循 HTTPS。例如，在设置 Cookie 时，需要按如下方式配对属性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果标记不正确，则较新的浏览器将无法使用Cookie，并将拒绝。

* `Lax`:允许使用同一站点Cookie发送跨站点请求，仅用于使用安全(只读 ** ，如)HTTP方法进行顶 `GET`级导航。

* `Strict`：不会为任何第三方网站请求发送相同站点 Cookie。仅当 Cookie 的站点与 URL 栏中的站点匹配时，才会发送 Cookie。

这些浏览器版本中的默认行为是将没有指定 `SameSite` 属性的 Cookie 视为与 `SameSite=Lax` 相同。

### Analytics如何管理SameSite Cookie属性？

对于使用访客 ID服务的客户，Cookies的属性`SameSite=None`和`secure`在默认情况下设置，这允许这些Cookies支持第三方使用案例。

对于使用Analytics旧版标识符（“s_vi”和“s_fid”cookies）的客户，还会将cookies设置为启用标准集合域的第三方使用案例：adobedc.net、2o7.net和omtrdc.net。 对于使用CNAME实施的客户，Analytics会设置`SameSite=Lax`。

>[!NOTE]
>
>如果您拥有多个域，并在您的所有域中使用相同的CNAME进行数据收集，则Cookie将作为其他域上的第三方Cookie。 如果您使用旧版Analytics标识符，则可能希望将您的设置更新为`SameSite=None`，以便这些Cookie可以在您的网站间共享。 有关详细信息，请参阅下一节中的“[当您对多个域使用一个CNAME时，更改SameSite值](#samesite-one-cname)”。

对于Google在`SameSite`设置为`None`时已识别为处理错误的Cookie的浏览器，请保持未设置`SameSite`。

下表汇总了Analytics Cookie的SameSite属性：

![Cookie 表](/help/technotes/assets/cookies1.png)

### 我的站点如何满足SameSite属性的要求？

#### 使用HTTPS服务所有网页

确认您的JavaScript配置对Adobe服务的所有调用使用HTTPS。

如果您的站点使用Experience Cloud访客ID服务，则服务会将第三方HTTP调用重定向到其HTTPS端点，这会增加延迟，但意味着您不需要更改配置。

#### 对多个域{#samesite-one-cname}使用一个CNAME时，更改SameSite值

>[!NOTE]
>
>以下信息仅适用于未使用Experience Cloud访客ID服务的站点。

如果您的CNAME实现与您的网站设置在同一域中，则Cookie是在第一方上下文中创建的，您无需进行更改。

但是，如果您拥有多个域，并在所有域中使用相同的CNAME进行数据收集，则Cookie将被视为其他域上的第三方Cookie。 在Chrome 80及更高版本中，它在这些其他域中不再可见。 为了使所有浏览器的行为更相似，Analytics已明确将此Cookie的`SameSite`值设置为`Lax`。 如果您在友好的第三方上下文中使用此Cookie，则必须设置具有`SameSite=None`值的Cookie，这也意味着您必须始终使用HTTPS。 如果您尚未这样做，请与Adobe客户服务部门联系，以便为您的安全CNAME更改SameSite值。

## 如何确定Safari更改是否影响我的业务？{#measure-itp-effect}

Adobe建议客户在更改数据收集之前，在自己的公司内衡量影响。 您可以使用Analysis Workspace衡量ITP跟踪预防对您的个别业务的影响：

* 衡量来自ITP管理的浏览器的流量百分比：

   1. 创建细分，了解有多少访客在使用ITP平台。

      >[!NOTE]
      >
      >受ITP影响的特定浏览器取决于您是否使用CNAME实现。 有关详细信息，请参阅“[ITP策略重大更改的时间线](#ITP-timeline)”。

      ![ITP访客细分](/help/technotes/assets/itp-visitor-segment.png)

   2. 将区段应用于访问次数，以了解Safari在用户群中的相对使用情况。 这样，您就可以创建这样的表：

      ![按ITP访客的访问百分比](/help/technotes/assets/visits-vs-safari-visits.png)

* 使用七天内未返回的非Safari浏览器衡量访客的百分比。 如果您的非Safari访客在七天内重复返回，则您的Safari流量可能不会受到重大影响。

   1. 为非Safari流量创建如下区段。

      ![针对七天后返回的访客的细分](/help/technotes/assets/visits-after-seven-days.png)

   2. 将区段应用于访问次数，以了解Safari在用户群中的相对使用情况。 这样，您就可以创建这样的表：

      ![七天后返回的访客百分比](/help/technotes/assets/percent-visits-after-seven-days.png)

### 在报告期间调整数据的方法

如果您的业务受到ITP跟踪预防的影响，您可以考虑以下措施在报告期间调整您的数据。

* 创建区段以筛选ITP用户。

   ![非ITP访客](/help/technotes/assets/non-itp-visitor-segment.png)

* 创建计算量度以调整已知访客通胀。

   ![计算量度以调整访客通胀](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[减轻浏览器Cookie限制影响的选项](cookieless.md)
>[Apple新应用程序跟踪透明度框架对Adobe Analytics的影响](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
