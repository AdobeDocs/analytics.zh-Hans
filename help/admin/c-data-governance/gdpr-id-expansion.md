---
description: '您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics 可创建一个扩展的 ID 集，以便将此关联数据包含在数据隐私请求中。您可以为您提交的每个数据隐私请求来要求使用此选项，只需将以下可选参数添加到 JSON 请求即可 '
title: ID 扩展
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# ID 扩展

您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics 可创建一个扩展的 ID 集，以便将此关联数据包含在数据隐私请求中。您可以为您提交的每个数据隐私请求来要求使用此选项，只需将以下可选参数添加到 JSON 请求即可：

```
"expandIds": true
```

有关如何在请求中包含此选项的示例，请参阅 [JSON 请求示例](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request)。有关更多详细信息，请参阅[隐私服务 API 文档](https://www.adobe.io/apis/experienceplatform/gdpr.html)。

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 类型 </th> 
   <th colname="col2" class="entry"> 注意事项 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID扩展 </p> </td> 
   <td colname="col2"> <p>许多 Analytics 客户最初使用（旧版）<a href="https://marketing.adobe.com/resources/help/zh_CN/whitepapers/cookies/cookies_analytics.html">Analytics Cookie</a>，但现在逐渐使用 <a href="https://marketing.adobe.com/resources/help/zh_CN/mcvid/">Identity 服务 (ECID)</a>，这项服务以前称为 Marketing Cloud ID 服务 (MCID)。对于在过渡后首次访问过的网站访客，仅存在ECID。 但是，对于那些在仅旧版Cookie可用时首次访问但此后已访问过的用户：其中一些数据将同时包含cookie，但旧数据将仅包含Analytics Cookie，而在少数情况下，最新数据可能仅包含ECID。 </p> <p>您需要确保找到通过Analytics(访客ID)Cookie或ECID标识的访客的所有数据。 因此，如果您当前使用ECID并且之前使用了Analytics Cookie，则每当您使用任一类型的ID提交请求时，都应在请求中包含这两个ID，或指定expandIds选项。 当您指定expandId时，Adobe将检查与您提供的任何cookie ID对应的其他ECID或Analytics Cookies。 该请求将自动扩展以包括这些新识别的cookie ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义ID到Cookie ID扩展 </p> </td> 
   <td colname="col2"> <p>在电子商务网站上，访客浏览网站、将物品添加到购物车中，然后在登录到网站之前开始结帐过程并不少见。 若用于识别数据隐私请求的用户 ID 仅在该用户登录后才存储在自定义变量中，则此类登录前进行的活动将不会与该 ID 关联。利用 Analytics Cookie ID，客户可以选择将登录之前执行的浏览与登录之后的购买关联，因为 Cookie ID 在整个登录过程中持久保留。 </p> <p>我们假设，您的实施将登录 ID（CRM ID、用户名、会员号、电子邮件地址等，或任何这些值的哈希值）存储在自定义变量（prop 或 eVar）或自定义访客 ID 中，然后将该 ID 用于数据隐私访问请求。数据主体可能会对此感到惊讶：关于他们浏览的信息并没有作为访问请求的一部分返回，特别是当您向他们推销了他们查看过但尚未购买的产品时。 </p> <p>因此，Analytics 数据隐私处理支持 ID 扩展，其中，Analytics 可找到在同一点击中出现的作为任何自定义 ID 的所有 Cookie ID，然后扩展该请求以一并包含这些 ID。 </p> <p>当expandID与Cookie命名空间以外的任何命名空间一起指定时，请求将展开以包括在包含任何指定ID的点击中找到的任何Cookie ID（ECID或Analytics Cookie）。 Cookie ID扩展（如上所述）随后将对任何新找到的Cookie ID执行。 </p> <p>当expandIDs选项用于访问请求且指定的ID的标签为ID-PERSON时，将返回两组文件。 第一个集（人物集）将仅包含在找到指定ID的点击中的数据。 第二组（设备集）将仅包含来自扩展ID的点击数据，其中不存在指定ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在数据隐私法正式生效后的前几个月，绝大多数的 Analytics 数据隐私请求都没有请求 ID 扩展，而需要您自行确定适合您组织的合适值。您应咨询您的法律团队，了解您使用的ID和您在Adobe Analytics中收集的数据是否需要ID扩展。 主要考虑的问题应该是，在共享设备上（多个用户已从共享设备访问过您的站点），使用ID扩展将包括来自设备其他用户的点击数据，该数据位于访问请求返回的数据中（在设备文件中）。 即使您在标签方面遵循了最佳实践，如设备文件中不包括专用数据（如访问的页面），设备文件也将包含访问的页面数量和每次访问的时间。 如果您与可能不是访客的人共享此信息，可以吗？

对于删除请求，如果不使用ID扩展，则您使用非cookie ID（ECID或Analytics Cookie以外的任何ID）来标识应删除的点击量，并且该ID具有ID-DEVICE标签，则报告中的唯一访客计数将会更改，因为只有cookie ID的某些实例将匿名化，而其他实例将保持不变。 如果未指定ID扩展，则建议您为请求使用Cookie ID，或使用带ID-PERSON标签的ID。

当Adobe执行ID扩展时，可能需要额外的完全数据扫描，这将增加Adobe完成请求所需的时间，通常会增加一周的处理时间。

## 其他数据隐私请求标记

除了“expandIDs”标记之外，Analytics 还支持另外两个可以作为数据隐私请求的组成部分传递的标记。这些标记的默认值为：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

将来，除了默认值“anonymize”之外，“analyticsDeleteMethod”还可能支持“purge”值。如果支持此值，它将会导致整个点击被删除，而不是简单地更新具有 DEL 标签的点击字段的值。

除默认值外，优先级字段还支持“low”值。您应该为数据主体请求以外的请求指定此值，这样便没有了必须在 30 天内完成的法律要求。请注意，Adobe 建议您不要因为数据主体发起请求以外的其他原因而使用数据隐私 API。数据隐私 API 是一个不适用于数据清理或修复的工具，会产生意想不到的后果。

>[!NOTE] 提供[隐私服务 API](https://www.adobe.io/apis/experienceplatform/gdpr.html) 是为了帮助您执行对时间敏感的数据隐私请求。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将隐私服务 API 用于其他目的，例如清除大量访客意外提交的数据。

您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。下次访客返回您的网站时，它们将成为新的访客。 所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了隐私服务 API 不适合此用途的一个原因。

请联系您的客户经理 (CSM) 来与我们的工程架构师咨询团队进行协调，以进一步审查并提供解决任何 PII 或数据问题的帮助。

