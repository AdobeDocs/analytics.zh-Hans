---
title: 跨设备访客识别常见问题解答
description: 关于跨设备访客识别的常见问题解答
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: 'https://experienceleague.adobe.com/RBciiyfaq671zJ51QdJJDXcekFr-lfq0WPY0UAuWoVA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# 跨设备访客识别常见问题解答

关于跨设备访客识别的常见问题解答。

+++跨设备访客识别与跨设备分析之间有何区别？
跨设备访客识别使用 `visitorID` 变量将设备绑定在一起，但存在一些主要限制。 此识别方法的一个最大限制便是：除非已经识别了设备，否则会排除未经验证的点击。 这些未经验证的点击可能会导致您的独特访客计数虚增。

跨设备分析是 Adobe 最新的跨设备访客识别方法。 它使用Experience Cloud ID服务和基于字段的拼合功能，以可追溯的方式将来自不同设备的访问拼合在一起。 CDA 需要使用 `setCustomerIDs` 函数来确定同一访客使用了哪些设备。
+++

+++跨设备访客识别如何处理区段？
跨设备访客识别对区段的处理方式与其他功能类似。 它会检查每次点击，以确认点击是否符合区段标准，如果符合，则会在数据中包括这些点击。 使用基于访问和访客的容器的区段仍会检查访客 ID。 确保您的实施尽可能使用 `visitorID` 变量，以便能一致识别独特访客并对其进行分段。
+++
