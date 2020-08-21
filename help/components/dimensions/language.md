---
title: 语言
description: 浏览器中的首选语言设置。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---


# 语言

“语言”维度显示访客喜欢在其中查看内容的最常用语言。当您想要了解访客最常使用的语言以帮助进行本地化时，此维度很有用。

>[!NOTE]
>
>此维度不会收集网站的语言。如果要在某个维度中收集网站的语言，Adobe 建议使用自定义变量，例如 [eVar](evar.md)。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `Accept-Language` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform Launch），则此维度可开箱即用。

## Dimension项

Dimension项包括首选访客语的友好名称。 示例包括 `"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"` 和 `"Spanish (Spain)"`。If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
