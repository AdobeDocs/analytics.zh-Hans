---
description: '您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics可以创建扩展的ID集，以将此关联数据包含到数据隐私请求中。 您可以向提交的每个数据隐私请求请求（添加到JSON请求中）请求此选项并带有可选参数 '
seo-description: '您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics可以创建扩展的ID集，以将此关联数据包含到数据隐私请求中。 您可以向提交的每个数据隐私请求请求（添加到JSON请求中）请求此选项并带有可选参数 '
seo-title: ID 扩展
title: ID 扩展
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# ID 扩展

您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics可以创建扩展的ID集，以将此关联数据包含到数据隐私请求中。 您可以向提交的每个数据隐私请求请求（添加到JSON请求中）请求此选项并添加一个可选参数：

```
"expandIds": true
```

有关如何在请求中包含此选项的示例，请参阅 [JSON 请求示例](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request)。For more details, refer to the [Privacy Service API documentation.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 类型 </th> 
   <th colname="col2" class="entry"> 注意事项 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID 扩展 </p> </td> 
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external"> Analytics Cookie </a>, but are now using the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). 对于在转换后首次访问这些客户网站的访客，仅存在 ECID。但是，对于那些在仅可使用旧版 Cookie 时首次访问，但之后又访问过的访客，他们的某些数据将同时具有这两个 Cookie，但是较旧的数据将只有 Analytics Cookie，而在极少数情况中，最新的数据可能只有 ECID。 </p> <p>您需要确保通过 Analytics（访客 ID）Cookie 或 ECID 识别的访客的所有数据都能被找到。因此，如果您以前使用过 Analytics Cookie 且现在使用 ECID，则当您使用任一类型的 ID 提交请求时，应在请求中包含两种 ID，或者指定 expandIds 选项。当您指定 expandIds 时，Adobe 将检查与您提供的任何 Cookie ID 相对应的其他 ECID 或 Analytics Cookie。该请求将自动扩展以包含这些新识别的 Cookie ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义 ID 转 Cookie ID 扩展 </p> </td> 
   <td colname="col2"> <p>在电子商务网站上，通常会有访客在登录到网站之前，先在网站内四处浏览，将商品添加到购物车，然后开始结账过程。如果用于标识数据隐私请求的用户的ID仅在用户登录时存储在自定义变量中，则此登录前活动将不与该ID关联。 利用 Analytics Cookie ID，客户可以选择将登录之前执行的浏览与登录之后的购买关联，因为 Cookie ID 在整个登录过程中持久保留。 </p> <p>假设您的实施将登录ID（CRM ID、用户名、忠诚度编号、电子邮件地址等，或这些值中任意一个的哈希值）存储在自定义变量（prop或eVar）或自定义访客ID中，然后将此ID用于数据隐私访问请求。 数据主体可能会对此感到惊讶：关于他们浏览的信息并没有作为访问请求的一部分返回，特别是当您向他们推销了他们查看过但尚未购买的产品时。 </p> <p>因此，分析数据隐私处理支持ID扩展，在该扩展中，Analytics会查找与任何自定义ID在同一点击中发生的所有Cookie ID，然后扩展请求以包含这些ID。 </p> <p>当指定了 expandIDs 以及 Cookie 命名空间以外的任何命名空间时，该请求将会扩展为包括任何在包含任意指定 ID 的命中中找到的 Cookie ID（ECID 或 Analytics Cookie）。如上所述，之后将会在任何新找到的 Cookie ID 上执行 Cookie ID 扩展。 </p> <p>当 expandIDs 选项用于访问请求且指定的 ID 具有 ID-PERSON 标签时，将返回两组文件。第一组（人员组）将仅包含来自命中项的数据，在这些命中当中发现了指定的 ID。第二组（设备组）将仅包含来自扩展 ID 的命中数据，且在这些命中当中不存在指定的 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在数据隐私开始生效后的头几个月中，绝大多数Analytics数据隐私请求都未请求ID扩展，但需要由您决定组织的适当值。 您应该咨询您的法律团队，了解包含您使用的 ID 的数据以及您在 Adobe Analytics 中收集的数据是否需要 ID 扩展。一个主要考虑因素是，在一台共享设备上，如果有多个用户使用该设备访问过您的网站，那么使用 ID 扩展后，在访问请求返回的数据中，将包括来自该设备其他用户命中项的数据（在设备文件中）。即使您遵循了标签设置的最佳实践使得设备文件中不含任何私人数据，例如访问过的页面，设备文件仍将包含访问过的页面数量以及每次访问的时间。是否可以与不是访客的人共享此类信息？

对于没有使用 ID 扩展的删除请求，如果您使用非 Cookie ID（除 ECID 或 Analytics Cookie 之外的任何 ID）来识别应删除的命中项，且该 ID 带有一个 ID-DEVICE 标签，那么报表中的独特访客计数将发生变化，因为只有部分 Cookie ID 的实例会被匿名化处理，而其他实例则保持不变。如果您没有指定 ID 扩展，则建议您在请求中使用 Cookie ID，或者使用带有 ID-PERSON 标签的 ID。

Adobe 在执行 ID 扩展时，可能需要进行额外的完整数据扫描，这将延长 Adobe 用于完成请求的时间，通常会增加一周的处理时间。

## 其他数据隐私请求标记

除了“expandIDs”标记外，Analytics还支持另外两个标记，这些标记可以作为数据隐私请求的一部分传递。 这些标记的默认值为：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

将来，“analyticsDeleteMethod”除了默认值“anonymize”之外，还可能支持“purge”值。 如果支持此值，它将会导致整个点击被删除，而不是简单地更新具有 DEL 标签的点击字段的值。

除了默认值之外，优先级字段还支持“low”值。 您应该为数据主体请求以外的请求指定此值，这样便没有了必须在 30 天内完成的法律要求。请注意，Adobe不鼓励出于数据主体发起的请求以外的原因使用隐私服务API。 隐私服务API不是用于数据清理或修复的适当工具，并且会产生意外后果。

[!NOTE]
已 [经提供Privacy Service API](https://www.adobe.io/apis/experienceplatform/gdpr.html) ，以帮助您完成数据隐私请求，这些请求是时间敏感的。 Adobe不支持将此API用于其他用途，并可能会影响Adobe为其他Adobe客户及时提供高优先级、由用户发起的数据隐私请求的能力。 我们要求您不要将Privacy Service API用于其他用途，如清除意外跨大量访客提交的数据。

您还应注意，因数据隐私删除请求而删除（更新或匿名化）点击的任何访客都将重置其状态信息。 这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问编号、反向链接、查看的首页等信息也都将重新显示。如果您要清除数据字段，则不会产生这种副作用，并且会突出说明隐私服务API不适合此用途的一个原因。

请联系您的客户经理(CSM)，与我们的工程架构师咨询团队协调，以进一步审查并提供删除任何PII或数据问题的工作量。

