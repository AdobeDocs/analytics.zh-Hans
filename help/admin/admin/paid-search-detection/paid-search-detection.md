---
description: '付费搜索检测可将搜索引擎和搜索关键词报表中的付费搜索与免费搜索区别开来。 '
title: 付费搜索检测
feature: 管理工具
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: b88f9d373d715b295dc4982a6ee05bd982f5bae7
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 71%

---

# 付费搜索检测

[!UICONTROL 付费搜索检测可将搜索引擎和搜索关键词报表中的付费搜索与免费搜索区别开来。]您可以指定在其中使用付费广告的搜索引擎，并且指定一个从访问付费广告的 URL 中找到的字符串。

## 配置选项 {#section_0C2CFA0AF77B47098BE37CB024665D0D}

下表介绍了用于[配置付费搜索检测](/help/admin/admin/paid-search-detection/t-paid-search-detection.md)的各个字段和选项。

| 选项 | 描述 |
| --- | --- |
| [!UICONTROL 搜索引擎] | 从下拉列表中选择一个搜索引擎。如果要对不同的搜索引擎使用不同的查询字符串参数，可指定引擎。通常，值`Any`就足够了。 |
| [!UICONTROL 查询字符串] | 为与查询字符串参数的任何部分（即URL中“？”后面的部分）的区分大小写匹配指定字符串。 <br>**注意**: [!UICONTROL 付费搜索] 检测区分大小写。例如，将“PID”指定为查询字符串参数的规则将与“pid”不匹配。 如果您的组织混用大小写，请将各个准确的值作为单独的规则，则可以捕获所有所需的查询字符串参数。 |
