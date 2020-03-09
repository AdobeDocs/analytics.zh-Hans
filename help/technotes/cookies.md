---
title: Adobe Analytics 和浏览器 Cookie
description: 了解 Adobe Analytics 处理如何浏览器 Cookie。
translation-type: ht
source-git-commit: 3566960f546d847ed4f6ca8ecbb9c759460f4fb0

---


# Adobe Analytics 和浏览器 Cookie

为了支持跨属性和解决方案的永久用户标识，Adobe Analytics 会对浏览器处理 Cookie 方式的更改做出响应。以下常见问题解答介绍了如何通过浏览器 Cookie 更改来保留永久访客标识。

## 浏览器如何更改其处理 Cookie 的方式？

通常，大多数浏览器在保存第三方 Cookie 方面的限制越来越严格。如果浏览器删除或拒绝 Cookie，这可能会影响跟踪。Safari 浏览器还为某些第一方 Cookie 设置了一些额外限制。

以下列表按浏览器显示了一些近期更改：

* Chrome：从 Chrome 80 开始，通过不同方式处理 `SameSite` 属性，以管理第三方 Cookie 或跨站点请求。最终，Chrome 开发人员正在寻找方法彻底[弃用第三方 Cookie](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1)。

* Firefox 和 Edge：产品公告指出，其浏览器的后续版本将遵循与 Chrome 80 中相同的更改。

* Safari：在 [Safari 12.1](https://webkit.org/blog/category/privacy/) 中，通过 document.Cookie API 设置的第一方持久性 Cookie（通常称为“客户端”Cookie）的有效期限最长为 7 天。

## 第三方 Cookie 和第一方 Cookie 有何区别？

### 第一方 Cookie

第一方 Cookie 由客户网站（特定于域）创建，并在用户访问客户网站时存储在客户端浏览器中。所有浏览器通常接受第一方 Cookie。在第一方 Cookie 分析实施中，当主机名与使用 [CNAME](https://docs.adobe.com/content/help/zh-Hans/id-service/using/reference/analytics-reference/cname.html) 的域协调一致时，会在 Adobe 节点上创建访客 ID Cookie。然后，浏览器在第一方上下文中接受该 Cookie。有关更多信息，请参阅[关于第一方 Cookie](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/ec-cookies/cookies-first-party.html)。

### 第三方 Cookie

第三方 Cookie 不是由用户访问的网站创建的。虽然浏览器当前对所有第三方 Cookie 的处理方式相同，并相应地进行存储，但第三方 Cookie 本身可以以不同的重要方式运行。通过客户的 Analytics 第三方 Cookie 实施，客户仅向 Adobe 发出调用，而不会向未知或可疑的第三方域发出调用。这是当前用于实施 Analytics 以通过持久标识符进行安全 (HTTPS) 可靠跟踪的方法。此方法通过配置 AppMeasurement.js 文件来实现。有关更多信息，请参阅 [Cookie 和 Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html)。

![Cookie 比较](assets/cookies2.png)

## 浏览器当前如何存储和管理 Analytics Cookie？

根据实施，Analytics Cookies 会按如下方式进行存储：

### 第三方 Cookie 实施

当前，浏览器将 Adobe [demdex.net](https://docs.adobe.com/content/help/zh-Hans/audience-manager/user-guide/reference/demdex-calls.html) ID 存储为第三方 Cookie。此 Cookie 提供跨域的永久标识符，并允许安全 (https) 内容。

### 第一方 Cookie 实施

通过配置 CNAME，您的用户可以在其浏览器的第一方 Cookie 上下文中接收 Adobe Cookie。如果第三方 Cookie 实施对您的用户来说不是最佳方案，则这是一个可行的选项。

## 什么是 SameSite Cookie 属性？该属性对 Analytics 有何影响？

随着 Chrome 80 浏览器以及 Firefox 和 Edge 浏览器后续版本的发布，SameSite Cookie 属性强制对三个不同值进行规范，以控制跨站点请求的行为，如下所示：

* `None`：此设置允许跨站点访问，并允许在第三方上下文中传递 Cookie。要指定此属性，您还必须指定 `Secure`，并且所有浏览器请求都必须遵循 HTTPS。例如，在设置 Cookie 时，需要按如下方式配对属性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正确标记，则 Cookie 将对于较新的浏览器不可用，并将被拒绝。

* `Lax`：允许使用&#x200B;*安全*（只读，如 `GET`）HTTP 方法，通过仅用于顶级导航的相同站点 Cookie 发送跨站点请求。

* `Strict`：不会为任何第三方网站请求发送相同站点 Cookie。仅当 Cookie 的站点与 URL 栏中的站点匹配时，才会发送 Cookie。

这些浏览器版本中的默认行为是将没有指定 `SameSite` 属性的 Cookie 视为与 `SameSite=Lax` 相同。

## Adobe Analytics 如何响应这些更改？

所有 Adobe Cookie 更新都通过 Adobe 服务器进行处理，Adobe 已更新其边缘服务器以设置相应的 Cookie 属性。Adobe 发布了服务器端更新，以使用相应的属性设置其第三方 Cookie。您的网站不需要进行 JavaScript 更新。

当用户访问使用 Cookie 的任何网站时，Adobe 边缘服务器将自动进行此升级。对于大多数 Adobe 产品，Cookie 在发布 Chrome 80 时会有相应的标记。Adobe Analytics 实施除外，这些实施使用第三方数据收集，并不使用 Experience Cloud Identity Service (ECID)。这些客户可能会遇到新访客数量的临时性增加，否则这些新访客将被标记为回访访客。

将 `SameSite` 设置为 `None` 时，对于被 Google 标识为错误处理 Cookie 的浏览器，`SameSite` 将保留为未设置。

下表汇总了 Analytics Cookie：

![Cookie 表](assets/cookies1.png)

## 为网站做好 Chrome、Firefox 和 Edge 更改准备的最佳方法是什么？

Analytics 客户应确认其 JavaScript 配置正在使用 HTTPS 来调用 Adobe 服务。ECID 将第三方 HTTP 调用重定向到其 HTTPS 端点，这会增加延迟，但也意味着您无需更改配置。

Adobe 建议您确保所有网站页面都通过 HTTPS 提供。

### 一个 CNAME 用于多个域

如果您的 CNAME 实施与网站设置在同一域中，则这将是第一方 Cookie 上下文，无需进行更改。

但是，如果您拥有多个域，并且在所有域中使用相同的 CNAME 进行数据收集，那么在这些其他域上，它将被视为第三方 Cookie。在 Chrome 80 中，该 CNAME 实施将不会再出现在这些其他域上。为了使所有浏览器的行为更相似，Analytics 明确将此 Cookie 的 `SameSite` 值设置为 `Lax`。如果您在友好的第三方上下文中使用此 Cookie，则需要使用 `SameSite=None` 值设置 Cookie，这也意味着您必须始终使用 HTTPS。请联系 Adobe 客户关怀部门，更改 SameSite 值，以获取安全的 CNAME。注意，使用 ECID 的 Analytics 客户不需要执行此操作。

## Safari 更改 (ITP 2.1) 对 Analytics 有何影响？

尽管 Safari 12.1 发生了更改，但仍从 Adobe Experience Cloud Cookie 中收集数据集。虽然 Cookie 的存储时间上限为七天，但在该时间内返回您属性的访客会更新 Cookie，以使存储时间再增加 7 天。在提供 Adobe 更新之前，Safari 流量的回顾窗口和回访访客计数可能会减少。

由于缩短了 7 天的存储期限，客户可能会看到独特访客有所增加。访问和页面查看次数应不会受到影响。如果您的属性具有季节性流量（如税务服务或假日零售），您可能面临更大的影响，因为此类访客在季节之间具有不连贯性。

如果您使用 CNAME，访客 ID 服务会将 ECID 保存到服务器端第一方 Cookie 中。这样可使 Cookie 在整个持续时间内保持不变。

**注意：ITP 2.1 不适用于移动应用程序中的嵌入式浏览器。**

### 受影响的第一方 Cookie

通过 `document.cookie` 创建的第一方 Cookie 会受影响。如果您通过 HTTP 响应（服务器端）或使用 CNAME 认证来设置这些 Cookie 中的任意一个，则不会受 ITP 2.1 中的更改的影响。以下第一方 Cookie 和相关的 Adobe JavaScript 库会受到影响：

* 由 ECID (Experience Cloud ID) 服务库设置的 AMCV Cookie
* Analytics 旧版回退 Cookie `s_fid`

基于 ITP 早期版本，作为第三方 Cookie 的 Analytics 旧版 `s_vi` Cookie（包括 2o7.net 或 omtrdc.net 的集合目标）仍将受到阻止。

综上所述：

* 如果您有 CNAME，并使用访客 ID 服务 - 您的实施不会受到影响。

* 如果您在第一方上下文中使用第一方 CNAME，但不使用访客 ID 服务 - 您的实施不会受到影响。

* 如果您在第三方上下文中使用第一方 Cookie 域，或使用标准第三方域名（如 2o7.net、omtrdc.net 等），Safari 将继续阻止。

* 如果您使用自定义访客 ID - 是否阻止取决于您如何存储访客 ID。如果您将 ID 存储在第一方“客户端”Cookie 中，则受七天到期限制。如果您使用其他方式存储您的自定义 ID，则需要评估自己是否受到影响。

### 影响最小的数据集

频繁回访的活动访客的数据集受更改影响最小。如果客户每天或每周至少回访数次您网站的内容，则这些活动用户的 Cookie 将在过期前续订。社交网络、新闻和其他媒体网站最有可能拥有大量频繁回访的用户社区。

使用 `s_vi` 作为主要访客 ID，并使用 CNAME 配置了第一方数据收集的客户不会受到 ITP 2.1 的影响。请注意，在无法设置 `s_vi` 的情况下，可以使用回退 Cookie `s_fid`，它将在七天后过期。

此外，使用访客 ID 服务并具有第一方域的数据集受到的影响最小。

## Safari 的更改是否会影响我的业务？

Adobe 建议客户在对数据收集进行任何更改之前，首先在自己的公司内部衡量影响。可以通过本节下面提供的方法进行衡量。

要衡量对报表和测试的影响，请务必了解已实施的访客和 Cookie 跟踪类型以及 Safari 用户的流量。请考虑以下因素，以衡量对个人业务的影响：

* 查看 Adobe 库正在设置哪些类型的 Cookie。

* 在最新的 Safari 浏览器中打开开发人员控制台。如果您在第一方域中看到以上列出的任何 Cookie，您可能会受到这些更改的影响。

* 如果您看到 `s_vi` Cookie，但未在 CNAME 上下文中看到 `AMCV` Cookie 集，则表示为访客标识使用 CNAME 以及 Analytics 使用情况不受这些更改的影响。如果您看到在 CNAME 上下文中设置了 `s_vi` Cookie 和 `AMCV` Cookie，则表示您最近或当前在使用宽限期，并且您的某些 Analytics 流量可能会受到影响。

* 使用 Analytics 衡量 7 天内未回访的访客百分比。如果访客在 7 天内反复回访，则流量可能不会受到显著影响。有关使用 Analtyics 确定是否受到影响的说明，请参阅 [Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

* 衡量来自 Safari 浏览器的流量百分比，以确定是否有必要进行任何更改。有关使用 Analtyics 确定您网站上 Safari 流量百分比的说明，请参阅 [Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我的访客最常使用哪些浏览器？

如果您有兴趣进一步了解访客使用的浏览器，可以使用 Analytics 的[浏览器维度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/variables/dimensions-reports/reports-browsers.html)来确定哪些浏览器最常用于您的网站。您还可以使用 Analytics 维度按地理区域查看最常使用的浏览器。有关更多信息，请参阅[地域划分](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html)。

根据[统计数据](https://gs.statcounter.com/browser-market-share/all)显示，2019 年底各浏览器的全球市场份额如下：

* Chrome：约 64%
* Safari：约 17%
* Firefox：约 4%
* Edge：约 2%

由于市场份额在不断变化，您可以参考这些[统计数据](https://gs.statcounter.com/browser-market-share/all)，以检查您的实施策略。

## 如何在短期内最好地运用 Safari 中的 ITP 2.1 更改？

Adobe 的 CNAME 和管理的证书计划将用于处理 ITP 更改。Adobe 管理的证书计划允许您在不增加任何额外费用的情况下，为第一方 Cookie 实施新的第一方证书。如今，Adobe 按解决方案提供了多项 CNAME 服务，并且希望在短期内利用 Analytics 认证计划。

如果当前 Analytics 客户设置了 CNAME，并且还使用 Experience Cloud ID 服务进行访客标识，则他们将能够利用将来的 ECID 库更新。此更改将允许 CNAME 认证的跟踪服务器维护 ECID，并将用作访客标识的参考。ECID 库的后续版本中提供了更多信息。

Adobe 了解到，并非所有 ECID 库客户都使用 CNAME 或 Analytics。将为所有 ECID 客户提供 CNAME 设置，以利用相同的功能。

如果您的实施当前没有利用 CNAME，则可以通过与客户关怀团队沟通来开始该过程。

## Adobe 关于持久访客标识的未来计划是什么？

新功能和实施包括：

* 跨所有 Adobe 解决方案的 CNAME 认证自助服务选项

* 灵活的访客 ID 收集方法、BYOI（自带身份标识）和优先 API 数据收集

* Adobe Experience Platform 的标识图

* 统一的 Adobe 数据收集方法

Adobe 致力于为希望获得个性化体验的消费者提供更准确的个性化服务。Adobe 努力为客户提供联机标识功能，帮助他们与客户的隐私选择保持一致。

## 更多信息

有关信息，请参阅：

* [Adobe Experience Cloud：Google Chrome 的 Cookie 更新](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1 对 Adobe Experience Cloud 和 Experience Platform 客户的影响](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)
