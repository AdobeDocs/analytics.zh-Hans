---
title: 中国地区的地区数据收集
seo-title: Adobe Analytics中国RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 中国地区的地区数据收集

Adobe 在中国大陆的地区数据收集 (RDC) 使中国地区的客户能够将数据直接发送到设在中国地区的数据收集中心 (DCC)，而不是位于世界其他地方的数据收集中心。与将数据发送到位于中国以外地区的 DCC 相比，这项更改可缩短页面加载时间，并提高数据准确性。

> [!IMPORTANT] 使用中国RDC节点会带来额外的成本。在使用本文档所述RDC节点在中国实施数据收集之前，请联系贵组织的客户经理以确保您有权获得此功能。

## 设置适用于中国的跟踪服务器

您可以在方便您提供服务的任何地区对中国的 RDC 进行跟踪。对于您希望路由到中国RDC的任何数字资产(例如移动应用程序或网页)，请将跟踪服务器更改为：

`<namespace>.sc.adobedc.cn`

请务必插入正确的命名空间。命名空间通常可以在现有跟踪服务器的开头处找到。For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. 您还可以将一个非 SSL 的第一方 [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) 记录指向这个新位置。

如果您的客户群中有任何大部分在中国之外，请不要将您的TrackingServer值设为全球范围内的所有属性和地理位置。应仅将中国地区客户的 trackingServer 设为“中国 RDC”值。否则，可能会对中国地区以外用户的访问速度带来负面影响，因为它会强制数据收集先转到中国，然后再返回以等待响应。

## 识别中国用户

如果您使用的是中国地区的 RDC 节点，那么不论您的数字资产托管在何处，或使用了何种语言，中国地区的用户体验都会得到改善。因此，建议的做法是先确定哪些用户位于中国，然后对这些用户使用“中国 RDC”。可帮助您识别此类用户的方法包括：

* 使用可靠的GeoIP解决方案。您可能决定使用服务器端解决方案轻松与Adobe Experience Platform Launch(或数据标签管理)集成。在这种情况下，可以通过在Experience Platform Launch或DTM对象中包含标准数据元素来确定位置。或者，您也可以使用客户端 GeoIP 解决方案。在这种情况下，Experience Platform Launch可以挂接到客户端代码中。请注意，此类解决方案可能会提示用户导航到本地化网站。这会带来一个风险，即第一页由全局跟踪服务器计算，第二页由中国的第二页计算，这可能会导致次计数。请遵循 GeoIP 解决方案的最佳实践。对于您所使用的 GeoIP 解决方案的准确度，Adobe 不承担任何责任。

* Using site structure or the browser language (the `navigator.language / accept-language` header). 这种方法的优点在于成本较低，且效果可能会更好。其缺点在于讲中文但在中国以外地区进行访问的访客会受到速度减慢的消极影响。
* 使用在中国的托管解决方案，并根据您的主机将TrackingServer设置为中国RDC。这也会大幅提高速度。

## 当前限制

中国RDC的最新限制：

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
2. 虽然 [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) 和 [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) 均受支持，但是由于 Target 和 Demdex 域不在中国大陆，因此无法享受到中国 RDC 范围内域所具有的速度或可靠性优势。

## Adobe 对中国地区的承诺

Adobe 计划不断完善中国 RDC，并将最终增加对诸如第一方 SSL 和服务器端转发等功能的支持。此外，Adobe 还计划在中国地区提供一个 Demdex 域（或等同的域），以便完全支持 ECID 和 Audience Manager 从中国地区收集数据。对于开始使用 Adobe 提供的中国 RDC 的客户，Adobe 欢迎其无限期地继续使用此数据收集端点。
