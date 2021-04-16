---
description: 内部 URL 过滤器可识别您视为存在于网站内部的反向链接。它们可帮助流量源报表填充数据，并且有助于过滤内部流量。
title: 内部 URL 过滤器
feature: 管理工具
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# 内部 URL 过滤器

**[!UICONTROL 管理员 > 报表包 > 编辑设置 > 常规 > 内部 URL 过滤器 > 添加过滤器]**

内部 URL 过滤器可识别您视为存在于网站内部的反向链接。它们可帮助流量源报表填充数据，并且有助于过滤内部流量。

反向链接或反向链接页面通常指访客通过该链接或页面进入了您的网站。为避免影响数据准确性，您可过滤掉内部的反向链接。报表不包含从[反向链接](/help/components/dimensions/referrer.md)维度、[反向链接域](/help/components/dimensions/referring-domain.md)维度和其他流量源维度中过滤掉的反向链接。

流量源报表不填充数据的最常见原因是未定义内部 URL 过滤器列表。要检查报表包上设置了哪些内部 URL 过滤器，请执行以下步骤。为了避免出现这种情况，请删除将句点 (.) 列为过滤器的规则，然后添加您自己的站点。

句点之所以成为默认的内部 URL 过滤器，是因为它允许在页面报表中收集数据。如果点击量不匹配内部 URL 过滤器，则所有页面会作为“其他”出现。句点总是位于 URL 中的某个位置，它可以确保填充页面报表。
