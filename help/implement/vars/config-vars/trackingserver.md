---
title: trackingServer
description: 用于通过HTTP向Adobe发送数据的域。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>此变量已弃用。 如果普遍使用HTTPS，请改用[`trackingServerSecure`](trackingserversecure.md)。

`trackingServer`变量可确定AppMeasurement用于通过HTTP向Adobe发送数据的域。 如果未正确定义此变量，则您的实施可能会丢失数据。

在[Adobe Experience Cloud Identity服务](https://experienceleague.adobe.com/zh-hans/docs/id-service/using/home)之前，此变量还确定第三方Cookie的设置位置。 Adobe强烈建议尽可能在所有实施中使用ID服务。

如果未设置`trackingServer`，AppMeasurement将使用[`trackingServerSecure`](trackingserversecure.md)作为回退。 许多旧实施未设置`trackingServerSecure`，在安全页面上使用`trackingServer`作为回退。 随着HTTPS的流行，Adobe建议尽可能使用`trackingServerSecure`。
