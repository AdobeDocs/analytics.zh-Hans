---
description: 当用户访问您的网站时，Adobe Web 服务器会设置一个永久性 Cookie，并将其包含在对浏览器的 HTTP 响应中。此 Cookie 是在指定的数据收集域中设置的。
keywords: Analytics 实施
seo-description: 当用户访问您的网站时，Adobe Web 服务器会设置一个永久性 Cookie，并将其包含在对浏览器的 HTTP 响应中。此 Cookie 是在指定的数据收集域中设置的。
seo-title: Analytics 访客 ID
solution: Analytics
title: Analytics 访客 ID
topic: 开发人员和实施
uuid: fa7737cc-0190-4d27-af1 b-87302a715 df2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analytics 访客 ID

当用户访问您的网站时，Adobe Web 服务器会设置一个永久性 Cookie，并将其包含在对浏览器的 HTTP 响应中。此 Cookie 是在指定的数据收集域中设置的。

请求发送至 Adobe 数据收集服务器后，将检查头是否存在访客 ID Cookie (`s_vi`)。如果此 Cookie 位于请求中，则将其用于识别访客。如果不在，服务器会生成一个唯一的访客 ID，并将其设置为 HTTP 响应头中的 Cookie，然后随请求发送回来。该 Cookie 会保存在浏览器中，并在后续访问该站点时发回到数据收集服务器，这也让系统能够在访客每次访问站点时对其进行识别。

## 第三方 Cookie 和 CNAME 记录 {#section_61BA46E131004BB2B75929C1E1C93139}

有些浏览器（如 Apple Safari）不再存储来源域与当前网站所在域不匹配的 HTTP 头中设置的 Cookie（这是第三方上下文中使用的 Cookie 或第三方 Cookie）。例如，如果您在 `mysite.com` 上，您的数据收集服务器为 `mysite.omtrdc.net`，那么从 `mysite.omtrdc.net` 的 HTTP 标头中返回的 Cookie 可能会遭到浏览器的拒绝。

为了避免这种情况，很多客户为其数据收集服务器实施了 CNAME 记录，以此作为[第一方 Cookie 实施](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)的一部分。如果 CNAME 记录被配置为将客户域上的主机名映射至数据收集服务器（例如将 `metrics.mysite.com` 映射至 `mysite.omtrdc.net`），则会存储访客 ID Cookie，因为数据收集域现在与网站的域相匹配。这提高了访客 ID Cookie 被存储的概率，但也会增加一些开销，因为需要为数据收集服务器配置 CNAME 记录并维护 SSL 证书。

## 移动设备上的 Cookie {#section_7D05AE259E024F73A95C48BD1E419851}

使用 Cookie 跟踪移动设备时，您可以使用某些设置修改测量方式。Cookie 的默认有效期为 5 年，但您可以使用 CL 查询参数变量 (`s.cookieLifetime`) 来更改此默认期限。要为 CNAME 实施设置 Cookie 位置，请使用 CDP 查询字符串 `s.cookieDomainPeriods`。如果不指定任何值，则默认值为 2。默认位置为 domain.com。对于不使用 CNAME 的实施，访客 ID Cookie 的位置位于 207.net 域中。
