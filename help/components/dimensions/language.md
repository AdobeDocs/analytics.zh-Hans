---
title: 语言
description: 浏览器中的首选语言设置。
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 语言

“语言”维度显示访客喜欢在其中查看内容的顶级语言。 当您想要了解最常使用的访客语语言以帮助本地化工作时，此维度很有价值。

> [!NOTE] 此维度不会收集站点的语言。 如果要在某个维度中收集站点的语言，Adobe建议使用自定义变量，如 [eVar](evar.md)。

## 用数据填充此维

此维引用Adobe内部的查找表。 查找值基于图像请 `Accept-Language` 求中的HTTP头。 如果您使用AppMeasurement库（如通过Adobe Experience Platform Launch），此维度将开箱即用。

## 维值

维值包括首选访客语言的友好名称。 Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. 如果图像请求在HTTP头中不包含有效语言，则维值为 `"None"`。
