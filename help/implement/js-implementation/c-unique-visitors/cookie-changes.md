---
description: Analytics Cookie
title: 浏览器和分析Cookie常见问题解答
uuid: null
translation-type: tm+mt
source-git-commit: ec96e30becf1cb799c0597b0e2f441fa1d6df0e3

---


# 浏览器和Analytics Cookies常见问题解答

为了支持跨属性和解决方案的永久用户识别，Adobe Analytics能够响应浏览器处理Cookie的方式的更改。 以下常见问题解答介绍了如何通过浏览器cookie更改来保留永久访客标识。

## 浏览器如何改变其处理Cookie的方式？

通常，大多数浏览器在保存第三方Cookie的方式上都变得更加限制。 如果浏览器删除或拒绝Cookie，这会影响跟踪。 Safari浏览器还为某些第一方Cookie设置了一些限制。

以下列表根据浏览器显示了一些最近的更改：

* Chrome:从Chrome 80开始，该属 `SameSite` 性会以不同方式处理，以管理第三方cookie或跨站点请求。 最终，Chrome开发人员正在寻找方 [法彻底弃用第三方Cookie](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) 。

* Firefox和Edge:产品公告指出，其浏览器的后续版本将遵循与Chrome 80中相同的更改。

* Safari: With [Safari 12.1](https://webkit.org/blog/category/privacy/), first party persistent cookies set through the document.cookie API, often known as “client-side” cookies, have their expiration capped at seven days.

## 第三方Cookie和第一方Cookie之间有何区别？

### 第一方 Cookie

第一方Cookie由客户网站（特定于域）创建，并在用户访问客户网站时存储在客户浏览器中。 所有浏览器通常接受第一方Cookie。 在第一方Cookie分析实施中，当主机名与域通过使用 [CNAME协调时，访客ID cookie会在Adobe节点上创建](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html)。 然后，浏览器在第一方上下文中接受该cookie。 有关详细信息，请 [参阅关于第一方Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)。

### 第三方Cookie

第三方Cookie不是由用户访问的网站创建的。 虽然浏览器当前对所有第三方Cookie的处理方式相同并相应地存储它们，但第三方Cookie本身的行为方式可能不同而重要。 通过客户的Analytics第三方Cookie实施，客户仅向Adobe发出呼叫，而不向未知或可疑的第三方域发出呼叫。 这是用于实施Analytics以实现安全(HTTPS)和使用永久标识符进行可靠跟踪的当前方法。 通过配置AppMeasurement.js文件来实现此方法。 有关详细信息，请参 [阅Cookie和Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)。

## 浏览器当前如何存储和管理Analytics cookies?

根据实施，Analytics Cookies会按如下方式存储：

### 第三方Cookie实施

浏览器当前将Adobe [demdex.net](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/demdex-calls.html) ID存储为第三方Cookie。 此Cookie提供跨域的永久标识符并允许安全(https)内容。

### 第一方Cookie实施

通过配置CNAME，您的用户可以在其浏览器的第一方Cookie上下文中接收Adobe Cookie。 如果第三方Cookie实施对您的用户来说不是最佳方案，则这可能是一个可行的选项。

## 什么是SameSite cookie属性，它对Analytics有何影响？

随着Chrome 80浏览器的发布以及Firefox和Edge浏览器的后续版本，SameSite cookie属性强制对三个不同值进行规范，以控制跨站点请求的行为，如下所示：

* `None`:此设置允许跨站点访问，并允许在第三方上下文中传递Cookie。 要指定此属性，您还必须指定， `Secure` 并且所有浏览器请求都必须遵循HTTPS。 例如，在设置Cookie时，需要按如下方式配对属性的值： `Set-Cookie: example_session=test12; SameSite=None; Secure`. 如果未正确标记，则Cookies对于较新的浏览器不可用，并将被拒绝。

* `Lax`:允许使用安全 ** （只读，如）HTTP方法，仅对顶级导航使用同一站点Cookie发送跨站点请求 `GET`。

* `Strict`:不会为任何第三方网站请求发送同一站点Cookie。 仅当cookie的站点与URL栏中的站点匹配时，才会发送cookie。

这些浏览器版本中的默认行为是将没有指定属性的Cookie `SameSite` 视为相同 `SameSite=Lax`。

## Adobe Analytics如何响应这些更改？

所有Adobe cookie更新都通过Adobe服务器进行处理，Adobe已更新其边缘服务器以设置相应的Cookie属性。 Adobe发布了服务器端更新，以使用相应的属性设置其第三方Cookie。 您的站点不需要JavaScript更新。

当用户访问使用Cookie的任何网站时，Adobe边缘服务器将自动进行此升级。 对于大多数Adobe产品，Cookies在发布Chrome 80时会有相应的标记。 Adobe Analytics实施除外，这些实施使用第三方数据收集，但不使用Experience Cloud Identity Service(ECID)。 这些客户可能会遇到新访客数量的临时性小增，否则这些新访客将被标记为回访访客。

对于Google在设置为时已识别为处理Cookie `SameSite` 的浏览器 `None`, `SameSite` 将取消设置。

下表汇总了Analytics cookie:


[分析Cookie表]


## 为Chrome、Firefox和Edge更改准备我的站点的最佳方式是什么？

分析客户应确认其JavaScript配置使用HTTPS来调用Adobe服务。 ECID将第三方HTTP调用重定向到其HTTPS端点，这会增加延迟，但意味着您无需更改配置。

Adobe建议您确保所有网站页面都使用HTTPS。

### 一个CNAME用于多个域

如果您的CNAME实现与网站设置在同一域中，则这将是第一方Cookie上下文，您无需进行更改。

但是，如果您拥有多个域，并且在所有域中使用相同的CNAME进行数据收集，那么在这些其他域上，它将被视为第三方Cookie。 在Chrome 80中，它将不再在这些其他域上可见。 为了使所有浏览器的行为更相似，Analytics明确将 `SameSite` 此Cookie的值设置为 `Lax`。 如果您在友好的第三方上下文中使用此Cookie，则需要将Cookie设置为值，这也意味 `SameSite=None` 着您必须始终使用HTTPS。 请联系Adobe客户关怀部门，为您的安全CNAME更改SameSite值。 注意，使用ECID的Analytics客户不需要执行此操作。

## Safari更改(ITP 2.1)对Analytics有何影响？

尽管Safari 12.1发生了更改，但仍在收集来自Adobe Experience Cloud Cookies的数据集。 虽然Cookies的上限为七天，但在该时间内返回您财产的访客会续订Cookie并防止其再过期七天。 在提供Adobe更新之前，可能会减少Safari流量的回顾窗口和回访访客计数。

由于缩短了七天的过期时间，客户可能会看到独特访客的增加。 访问和页面查看次数不应受到影响。 如果您的房产具有季节性流量（如税务服务或假日零售），您可能会看到更大的影响，因为此访客不会在季节之间连接。

如果您使用CNAME，访客ID服务会将ECID保存到服务器端第一方Cookie中。 这允许Cookie在整个持续时间内保持不变。

**注意：ITP 2.1不适用于移动应用程序中的嵌入式浏览器。**

### 受影响的第一方Cookie

通过创建的第一方Cookie `document.cookie` 受影响。 如果您通过HTTP响应（服务器端）或使用CNAME认证来设置这些Cookie中的任何一个，则不会受ITP 2.1中的更改的影响。以下第一方Cookie和相关的Adobe javaScript库受影响：

* 由ECID(Experience Cloud ID)服务库设置的AMCV Cookie
* 分析旧版回退cookie `s_fid`

作为第 `s_vi` 三方Cookie的分析旧版Cookie（包括2o7.net或omtrdc.net的集合目标）继续基于ITP的早期版本被阻止。

总之：

* 如果您有CNAME，并使用访客ID服务— 您的实施不会受到影响。

* 如果您在第一方上下文中使用第一方CNAME，但不使用访客ID服务— 您的实施不会受到影响。

* 如果您在第三方上下文中使用第一方Cookie域，或使用标准第三方域名（如2o7.net、omtrdc.net等）,Safari将继续阻止它。

* 如果您使用自定义访客ID — 这取决于您如何存储访客ID。 如果您将您的ID存储在第一方“客户端”Cookie中，那么您将面临七天的过期时间。 如果您使用其他方式存储您的自定义ID，那么您需要评估自己是否受到影响。

### 影响最小的数据集

频繁回访的活动访客的数据集受更改影响最小。 如果您网站的内容使客户每天或每周至少回访几次，则这些活动用户的Cookie将在过期前续订。 社交网络、新闻和其他媒体网站最有可能拥有大量频繁回访的用户社区。

使用ITP 2.1 `s_vi` 作为主要访客ID并配置了使用CNAME的第一方数据收集的客户将不会受到影响。请注意，在无法设 `s_vi` 置的情况下，可能会使 `s_fid` 用备用Cookie，并且将有七天的过期时间。

此外，使用访客ID服务并具有第一方域的数据集受到的影响最小。

## Safari的更改是否会影响我的业务？

Adobe建议客户在对数据收集进行任何更改之前，首先在自己的公司内部测量影响。 这可以通过本节下面提供的方法来完成。

要衡量对报告和测试的影响，请务必了解已实施的访客和cookie跟踪类型以及Safari用户的流量。 请考虑以下因素，以衡量对个人业务的影响：

* 检查Adobe库正在设置哪些类型的Cookie。

* 在最新的Safari浏览器中打开开发人员控制台。 如果您在您的第一方域中看到以上列出的任何cookie，您可能会受到这些更改的影响。

* 如果您看到 `s_vi` cookie，但未在CNAME上下文中设置 `AMCV` cookie，则表示您使用CNAME进行访客识别，且Analytics使用情况不受这些更改的影响。 如果您在CNAME上下文中看到 `s_vi` cookie和 `AMCV` cookie设置，则您最近或当前都在使用宽限期，并且您的某些Analytics流量可能会受到影响。

* 使用Analytics测量七天内未回访的访客百分比。 如果访客在七天内反复回访，则流量可能不会受到重大影响。 有关使用Analtyics找到此问题的说明，请参阅 [Safari ITP 2.1对Adobe Experience cloud和Experience platform客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

* 从Safari浏览器测量流量百分比，以确定是否有足够的保证进行更改。 有关使用Analtyics查找您的站点的Safari流量百分比的说明，请参阅 [Safari ITP 2.1对Adobe Experience cloud和Experience platform客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我的访客最常使用哪些浏览器？

如果您有兴趣进一步了解访客使用的浏览器，可以使用Analytics [Browser Dimension](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) （分析浏览器维度）来确定哪些浏览器最适合您的网站。 您还可以使用Analytics Dimensions来查看根据地理区域最常使用的浏览器。 For more information, see [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

根据 [统计](https://gs.statcounter.com/browser-market-share/all)，于2019年底，各浏览器的全球市场份额如下：

* Chrome:~64%
* Safari:~17%
* Firefox:~4%
* 边缘：~2%

随着市场份额的变化，您可以参考这些统计 [数据](https://gs.statcounter.com/browser-market-share/all) ，以检查您的实施战略。

## 如何在短期内最好地使用Safari中的ITP 2.1更改？

Adobe的CNAME和托管证书程序用于处理ITP更改。 Adobe 管理的证书计划允许您在不增加任何额外费用的情况下，为第一方 Cookie 实施新的第一方 证书。如今，Adobe按解决方案提供了多项CNAME服务，并且希望在短期内利用Analytics认证计划。

具有CNAME设置的任何当前Analytics客户（同时也使用Experience Cloud ID服务进行访客识别）都将能够利用将来的ECID库更新。 此更改将允许CNAME认证的跟踪服务器维护ECID并用作访客识别的参考。 ECID库的后续版本中提供了更多信息。

Adobe了解到，并非所有ECID库客户都使用CNAMES或Analytics。 所有ECID客户都将获得CNAME设置，以利用相同的功能。

如果您当前没有利用CNAME进行实施，则可以通过与客户关怀团队交谈来开始该过程。

## Adobe的持久访客识别未来计划是什么？

新功能和实施包括：

* 跨所有Adobe解决方案的CNAME认证自助服务选项

* 灵活的访客ID收集方法、BYOI（自带身份）和API-first数据收集

* Adobe Experience platform的标识图

* 统一的Adobe数据收集方法

Adobe致力于为希望获得个性化体验的消费者提供更准确的个性化体验。 Adobe努力为客户提供在线标识功能，帮助他们与消费者的隐私选择保持一致。

## 更多信息

有关信息，请参阅：

* [Adobe Experience Cloud:Google Chrome的Cookie更新](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1对Adobe Experience cloud和Experience Platform客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

