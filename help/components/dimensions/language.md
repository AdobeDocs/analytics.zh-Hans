---
title: 语言
description: 浏览器中的首选语言设置。
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# 语言

“语言”[维度](overview.md)显示访客喜欢在其中查看内容的最常用语言。 当您想要了解访客最常使用的语言以帮助进行本地化时，此维度很有用。

>[!NOTE]
>
>此维度不会收集网站的语言。如果要在某个维度中收集网站的语言，Adobe 建议使用自定义变量，例如 [eVar](evar.md)。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `Accept-Language` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

## 维度项目

维度项目包括访客首选语言的友好名称。示例包括 `"English (United States)"`、`"English (United Kingom)"`、`"Chinese (China)"` 和 `"Spanish (Spain)"`。如果图像请求在 HTTP 标头中不包含有效语言，则维度项目为 `"None"`。
