---
title: AMO 元广告点击 ID
description: Adobe Media Optimizer Meta广告点击ID，用于Adobe Advertising集成。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# AMO 元广告点击 ID

**[!UICONTROL AMO Meta广告点击ID]**&#x200B;是在Adobe Advertising集成中使用的广告点击标识符。 启用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)集成时，将自动创建维度。 它主要用作原始跟踪标识符，而不是人类可读的报表维度。

## 使用数据填充此维度

此维度通过多种方式收集其值：

* 对于点进流量，数据是从`fbclid`页面URL[中的](page-url.md)查询字符串参数收集的，通常是在广告驱动流量进入网站的页面上。
* 当URL不包含跟踪代码，但Adobe Advertising JavaScript在前两分钟内检测到点击时，也可以捕获点进流量。

## 维度项目

Dimension项目包括由Meta (Facebook)广告网络生成的广告点击标识符。 这些哈希值的长度可以有所不同，但通常为数百个字符。 示例（截断）值包括：

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
