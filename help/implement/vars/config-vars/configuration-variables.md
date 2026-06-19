---
title: 配置变量
description: 使用配置变量可帮助确定数据收集的方式。
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ccf6c5e3f25f562a3bfffe89b9ff057c28aab409
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 18%

---

# 配置变量概述

配置变量能够控制报表中捕获和处理数据的方式。 此类变量通常不包含维度或量度值。

## 设置配置变量

在使用Web SDK扩展或Analytics扩展的实施中，通常可以在扩展的设置中找到配置变量：

1. 使用您的Adobe Experience Platform凭据登录[Adobe ID数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 单击“扩展”选项卡，然后单击扩展下的“配置”。

在使用 `AppMeasurement.js` 的 JavaScript 实施中，通常会在 JS 文件的顶部设置配置变量。

>[!IMPORTANT]
>
>确保在调用跟踪方法（[`t()`](../functions/t-method.md)或[`tl()`](../functions/tl-method.md)）之前设置所有配置变量。 避免在 [`doPlugins()`](../functions/doplugins.md) 函数中设置配置变量。

## 已停用的配置变量

以下配置变量已停用。 如果您在旧版实施中遇到这些问题，请在此处记录这些问题以供参考。

* **`account`**：已确定将数据发送到的报表包。 报表包现在通过跟踪对象实例化（[`s_gi()`](../functions/s-gi.md)方法）进行处理。 如果在实例化跟踪对象后需要更改报表包，请使用[`s.sa()`](../functions/sa-method.md)方法。
* **`cookieDomain`**：已确定AppMeasurement设置Cookie的域。 AppMeasurement的当前版本会自动检测正确的Cookie域，从而使此变量失效。
* **`cookieDomainPeriods`**：帮助AppMeasurement确定当域包含多个句点时存储Cookie的位置。 当前版本的AppMeasurement会自动检测正确的域，从而使此变量失效。
* **`fpCookieDomainPeriods`**： `cookieDomainPeriods`的第一方等效项，用于在第一方域后缀包含额外句点（如`example.co.uk`）时在正确位置设置Cookie。 当前版本的AppMeasurement会自动检测正确的域，从而使此变量失效。
* **`trackingServer`**：指定用于通过HTTP向Adobe发送数据的域。 它已被弃用，支持优于HTTPS的安全数据收集。 请改用 [`trackingServerSecure`](trackingserversecure.md)。
* **`trackInlineStats`**：启用或禁用了[Activity Map](/help/analyze/activity-map/overview.md)的早期版本。
* **`visitorMigrationKey`**：带有用于将访客从第三方迁移到第一方Cookie的密钥。 此令牌已停用，因为现代库设置了第一方回退Cookie (`fid`)，并依赖Experience Cloud ID服务来获取身份。
* **`visitorMigrationServer`**：指定在第三方到第一方Cookie迁移期间使用的服务器。
* **`visitorMigrationServerSecure`**： `visitorMigrationServer`的HTTPS等效项。
* **`visitorNameSpace`**：帮助确定第三方Cookie域。 此服务已停用，以支持将[`trackingServerSecure`](trackingserversecure.md)变量用于不使用Experience Cloud ID服务的实施。
