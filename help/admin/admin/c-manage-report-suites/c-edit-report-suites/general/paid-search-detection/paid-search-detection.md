---
description: 付费搜索检测在“搜索引擎”和“搜索关键词”报表中区分付费搜索与免费搜索。
title: 付费搜索检测
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# 付费搜索检测

[!UICONTROL 付费搜索检测]在[!UICONTROL “搜索引擎”]和[!UICONTROL “搜索关键词”]报表中区分付费搜索与免费搜索。可指定从中使用付费广告的搜索引擎，并可指定在从付费广告访问的 URL 中找到的字符串。

## 配置选项 {#configuration}

下表介绍用于[配置付费搜索检测](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)的各个字段和选项。

| 选项 | 描述 |
| --- | --- |
| [!UICONTROL 搜索引擎] | 从下拉列表中选择一个搜索引擎。如果要对不同的搜索引擎使用不同的查询字符串参数，可指定引擎。一般使用 `Any` 值即可。 |
| [!UICONTROL 查询字符串] | 指定以区分大小写的形式与查询字符串参数（即 URL 中“?”后面的部分）的任何部分匹配的字符串。<br>**注意**：[!UICONTROL 付费搜索检测]区分大小写。例如，指定“PID”作为查询字符串参数的规则将不匹配“pid”。如果您的组织混用大小写，请将各个准确的值作为单独的规则，这样即可捕获全部所需的查询字符串参数。 |
