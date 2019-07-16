---
description: 地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。
keywords: Analytics 实施
seo-description: 地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。
seo-title: 地理分段数据
solution: Analytics
title: 地理分段数据
topic: 开发人员和实施
uuid: 8449bf11-c367-4698-a73 e-f6 cb59 f8 c945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 地理分段数据

>[!IMPORTANT]
>
>不再建议跨设备识别访客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

地域划分数据根据访问的首次点击进行记录，并且无论使用的是什么设备，单次访问的地域划分数据都不会更改。

如果客户从其家庭计算机中浏览您的网站，然后在 30 分钟内又从移动设备访问您的网站，则地域划分数据不会发生更改。如果您使用VISTA填充具有地理分段数据的eVar，则它基于每个点击中的IP地址。如果同一访问的IP地址发生变化，则会导致多个地理分段数据值。
