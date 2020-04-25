---
description: 针对变量设置某个值的次数。
keywords: instances
title: 实例
topic: Metrics
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 实例

针对变量设置某个值的次数。

实例所有点击类型都会计算实例数，但是在后续点击上针对变量记录值时将不计算实例数量，因为这会一直存留。

例如，如果用户通过 [!DNL example.com] 访问到您的网站，则您网站上的第一个图像请求包含了 [!DNL example.com] 反向链接。设置此值后，一个实例将归属于 [!DNL example.com]，即使针对该次访问期间查看的所有页面记录此反向链接也不例外。

Data Warehouse 中的转化变量实例是在 2011 年年中添加的，它使得 Data Warehouse 请求可将特定的转化变量实例视为一个量度。在引入这些量度之前，它们并不适用于报表。
