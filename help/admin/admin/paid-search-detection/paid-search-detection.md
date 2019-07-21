---
description: 付费搜索检测可将搜索引擎和搜索关键词报表中的付费搜索与免费搜索区别开来。您可以指定在其中使用付费广告的搜索引擎，并且指定一个从访问付费广告的 URL 中找到的字符串。
seo-description: 付费搜索检测可将搜索引擎和搜索关键词报表中的付费搜索与免费搜索区别开来。您可以指定在其中使用付费广告的搜索引擎，并且指定一个从访问付费广告的 URL 中找到的字符串。
seo-title: 付费搜索检测
solution: Analytics
title: 付费搜索检测
topic: 管理工具
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
translation-type: tm+mt
source-git-commit: ad6ba22acf6996aa038c5a3252cae8bddbf0b36a

---


# 付费搜索检测

付费搜索检测可将搜索引擎和搜索关键词报表中的付费搜索与免费搜索区别开来。您可以指定在其中使用付费广告的搜索引擎，并且指定一个从访问付费广告的 URL 中找到的字符串。

## 付费搜索检测 - 描述 {#section_0C2CFA0AF77B47098BE37CB024665D0D}

The following table describes the fields and options you use to [configure paid search detection](../../../admin/admin/paid-search-detection/t-paid-search-detection.md#task_D0BBDB78771E4BDBB495A004A080D647).

| 元素 | 描述 |
|--- |--- |
| 搜索引擎 | 从下拉列表中选择一个搜索引擎。如果要对不同的搜索引擎使用不同的查询字符串参数，可指定引擎。通常情况下，使用任意值即可。 |
| 查询字符串 | 指定区分大小写的规则集是否包含特定值。该值应为查询字符串参数，省略 "?". <br>**注意**：付费搜索检测区分大小写。例如，将PID指定为查询字符串参数的规则在报表中不显示pid。如果您的组织混用大小写，请将各个准确的值作为单独的规则，则可以捕获所有所需的查询字符串参数。</br> |