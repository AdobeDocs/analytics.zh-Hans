---
title: trackingServer
description: 用于通过HTTP向Adobe发送数据的域。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 19%

---

# trackingServer

>[!IMPORTANT]
>
>此变量已弃用。 如果普遍使用HTTPS，请改用[`trackingServerSecure`](trackingserversecure.md)。

`trackingServer`变量可确定AppMeasurement用于通过HTTP向Adobe发送数据的域。 如果未正确定义此变量，则您的实施可能会丢失数据。

在[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/cn/docs/id-service/using/home)之前，此变量还确定第三方Cookie的设置位置。 Adobe强烈建议尽可能在所有实施中使用ID服务。

如果未设置[`trackingServerSecure`](trackingserversecure.md)，AppMeasurement将使用`trackingServer`作为回退。 许多旧实施未设置`trackingServerSecure`，在安全页面上使用`trackingServer`作为回退。 随着HTTPS的流行，Adobe建议尽可能使用`trackingServerSecure`。
