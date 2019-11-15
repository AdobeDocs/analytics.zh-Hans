---
description: 地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。
keywords: Analytics Implementation
solution: Analytics
title: 地域划分数据
topic: Developer and implementation
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 地域划分数据

>[!IMPORTANT]
>
>不再建议使用这种方法来识别跨设备访客。请参阅 [Adobe Experience cloud设备协作文档](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。

如果客户从其家庭计算机中浏览您的网站，然后在 30 分钟内又从移动设备访问您的网站，则地域划分数据不会发生更改。如果通过 VISTA 使用地域划分数据填充 eVar，则该数据将基于每次点击的 IP 地址。如果同一次访问的 IP 地址发生更改，则可能会产生多个地域划分数据值。
