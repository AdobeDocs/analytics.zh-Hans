---
description: 付费搜索检测在“搜索引擎”和“搜索关键词”报表中区分付费搜索与免费搜索。
title: 付费搜索检测
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
TQID: https://experienceleague.adobe.com/g26-86nQZ-k3kaID-Dq6qbwYkdqLpHDdUEswP-p361Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 87%

---

# 付费搜索检测

[!UICONTROL 付费搜索检测]在[!UICONTROL “搜索引擎”]和[!UICONTROL “搜索关键词”]报表中区分付费搜索与免费搜索。 可指定从中使用付费广告的搜索引擎，并可指定在从付费广告访问的 URL 中找到的字符串。

## 配置选项 {#configuration}

下表介绍用于[配置付费搜索检测](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)的各个字段和选项。

| 选项 | 描述 |
| --- | --- |
| [!UICONTROL 搜索引擎] | 从下拉列表中选择搜索引擎。 如果为不同的搜索引擎使用不同的查询字符串参数，则可以指定引擎。 一般使用 `Any` 值即可。 |
| [!UICONTROL 查询字符串] | 指定以区分大小写的形式与查询字符串参数（即 URL 中“?”后面的部分）的任何部分匹配的字符串。 <br>**注意**：[!UICONTROL 付费搜索检测]区分大小写。 例如，指定“PID”作为查询字符串参数的规则将不匹配“pid”。 如果您的组织混用大小写，请将各个准确的值作为单独的规则，这样即可捕获全部所需的查询字符串参数。 |
