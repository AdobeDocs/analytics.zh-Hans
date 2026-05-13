---
title: 回访频率
description: 当前访问与上次访问之间存储的时间。
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 94%

---

# 回访频率

“回访频度”[维度](overview.md)显示回访访客两次访问之间经过的时间长度。 当访客回访您的网站时，Adobe 会查看上次访问的时间，并将点击记录在相应的维度项目中。 此维度有助于评估网站在一段时间内对访客的吸引力和相关性。 它还有助于确定网站内容和促销活动对访客的影响。

>[!TIP]
>
>此维度不包括首次访客。

## 使用数据填充此维度

此维度可开箱即用于所有实施。 如果报表包包含数据，则此维度有效。

此维度的数据是在访问的第一次点击时设置的，并在整个访问期间保留。 此值不能在访问中更改。

## 维度项目

维度项目包括基于时间的分段数量，具体取决于上次访问后经过的时间。

* 不到 1 天
* 1 到 3 天
* 3 到 7 天
* 7 到 14 天
* 14 天到 1 个月
* 超过 1 个月

## 维度项目显示在项目日期范围外的分段下

设置项目的日期范围时，通常会查看日期范围外促进访问的维度项目。 例如，访客在 7 月访问网站，然后在 9 月的同一天回访两次。 9 月份回访频率维度会在“超过 1 个月”下显示一次访问，并在“小于 1 天”下显示一次访问。
