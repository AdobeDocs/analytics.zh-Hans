---
description: 您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics 可创建一个扩展的 ID 集，以便将此关联数据包含在数据隐私请求中。您可以为您提交的每个数据隐私请求来要求使用此选项，只需将以下可选参数添加到 JSON 请求即可
title: ID 扩展
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: e9fffe62d3e53ae075610b1feec9a9071d925433
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 47%

---

# ID 扩展

您提交的 ID 并不总是涵盖 Analytics 可将其与数据主体关联的所有命中数据。Analytics 可创建一个扩展的 ID 集，以便将此关联数据包含在数据隐私请求中。您可以为您提交的每个数据隐私请求来要求使用此选项，只需将以下可选参数添加到 JSON 请求即可：

```
"expandIds": true
```

有关更多详细信息，请参阅[隐私服务 API 文档](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)。


| 类型 | 注意事项 |
| --- | --- |
| Cookie ID 扩展 | 许多Analytics客户最初使用（旧版） [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en)，但现在正在使用 [Experience Cloud标识服务(ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans). 对于在转换后首次访问这些客户网站的访客，仅存在 ECID。但是，对于那些仅在可用旧版Cookie时首次访问，但此后又访问过的用户：他们的某些数据同时具有两个cookie。 但是，旧数据仅具有Analytics Cookie，在极少数情况下，最新数据可能只具有ECID。<p>确保您找到通过Analytics（访客ID）Cookie或ECID识别的访客的所有数据。 如果您当前使用的是ECID，并且之前使用过Analytics Cookie，则每当您使用任一类型的ID提交请求时，都应在请求中包含这两个ID，或者指定 `expandIds` 选项。 指定 `expandIds`，则Adobe会检查与您提供的任何Cookie ID对应的其他ECID或Analytics Cookie。 请求会自动展开以包含这些新识别的Cookie ID。 |
| 自定义 ID 转 Cookie ID 扩展 | 在电子商务网站上，通常会有访客在登录到网站之前，先在网站内四处浏览，将商品添加到购物车，然后开始结账过程。如果用于识别数据隐私请求用户的ID仅在用户登录后才存储在自定义变量中，则此登录前活动与该ID不相关联。 利用 Analytics Cookie ID，客户可以选择将登录之前执行的浏览与登录之后的购买关联，因为 Cookie ID 在整个登录过程中持久保留。<p>我们假设，您的实施将登录 ID（CRM ID、用户名、会员号、电子邮件地址等，或任何这些值的哈希值）存储在自定义变量（prop 或 eVar）或自定义访客 ID 中，然后将该 ID 用于数据隐私访问请求。数据主体可能会对访问请求未返回有关其所有浏览的信息感到惊讶，特别是当您促销了已查看但尚未购买的项目时。 因此，Analytics 数据隐私处理支持 ID 扩展，其中，Analytics 可找到在同一点击中出现的作为任何自定义 ID 的所有 Cookie ID，然后扩展该请求以一并包含这些 ID。<p>When `expandIDs` 与Cookie命名空间以外的任何命名空间一起指定时，该请求会扩展为包含在包含任何指定ID的点击中找到的任何Cookie ID（ECID或Analytics Cookie）。 然后，会对任何新找到的Cookie ID执行如上所述的Cookie ID扩展。<p>当 `expandIDs` 选项，并且指定的ID具有ID-PERSON标签，则将返回两组文件。 第一组（人员组）将仅包含来自命中项的数据，在这些命中当中发现了指定的 ID。第二组（设备组）将仅包含来自扩展 ID 的命中数据，且在这些命中当中不存在指定的 ID。 |

{style=&quot;table-layout:auto&quot;}

## 何时使用ID扩展

在数据隐私法正式实施后的头几个月，绝大多数的Analytics数据隐私请求都没有请求ID扩展。 但是，您需要确定贵组织的适当值。 您应当咨询您的法律团队，以了解是否需要ID扩展才能获取包含您使用的ID以及您在Adobe Analytics中收集的数据。

主要考虑事项应是：在多个用户都从共享设备访问过您的网站的共享设备上，使用ID扩展将包括来自其他用户对设备点击的数据，这些数据包含在访问请求返回的数据中（在设备文件中）。 即使您遵循了标签设置的最佳实践（例如，设备文件中不包含任何私有数据，如访问过的页面），设备文件中也包含访问过的页面数量和每次访问的时间。 问问你自己：如果您与可能不是访客的人共享此信息，是否可以？

当ID扩展为 *not* 用于删除请求：如果您使用非Cookie ID（ECID或Analytics Cookie以外的任何ID）来识别应删除的点击量，并且该ID具有ID-DEVICE标签，则报表中的独特访客计数会发生更改。 这是因为只有Cookie ID的一些实例将匿名化，而其他实例将保持不变。 如果您没有指定ID扩展，那么我们建议您对请求使用Cookie ID，或者使用带有ID-PERSON标签的ID。

当Adobe执行ID扩展时，可能需要进行额外的完整数据扫描。 这会增加Adobe完成请求所花费的时间，通常会在处理时间上增加一周。

## 其他数据隐私请求标记

除了“expandIDs”标记之外，Analytics 还支持另外两个可以作为数据隐私请求的组成部分传递的标记。这些标记的默认值为：

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

未来， `analyticsDeleteMethod` 除默认值“anonyize”外，可能还支持值“purge”。 如果支持，它将导致删除整个点击，而不是简单地更新具有DEL标签的点击字段的值。

除默认值外， `priority` 字段还支持值“low”。 您应该为数据主体请求以外的请求指定此值，这样便没有了必须在 30 天内完成的法律要求。

## Privacy ServiceAPI的使用

>[!IMPORTANT]
>
>Adobe不建议使用 [Privacy ServiceAPI](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans) 除数据主体启动的请求之外的其他原因。 数据隐私 API 是一个不适用于数据清理或修复的工具，会产生意想不到的后果。提供Privacy ServiceAPI是为了帮助您执行对时间敏感的数据隐私请求。 Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将隐私服务 API 用于其他目的，例如清除大量访客意外提交的数据。

您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了隐私服务 API 不适合此用途的一个原因。

请联系您的客户经理 (CSM) 以与我们的工程架构师咨询团队进行协调，以进行进一步审查并提供解决任何 PII 或数据问题的帮助。
