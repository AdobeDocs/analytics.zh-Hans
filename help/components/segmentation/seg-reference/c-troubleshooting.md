---
description: 了解如何排除和修复与区段相关的问题。
title: 故障排除
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 42%

---

# 故障排除

本文列出了区段的一些常见问题以及如何解决这些问题。

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## 为何我的区段根本不返回任何数据？ {#no-data}

可能的原因：

* 反向嵌套 — 例如，在![访问](/help/assets/icons/User.svg) **[!UICONTROL 访问]**&#x200B;容器下嵌套![用户](/help/assets/icons/Visit.svg) **[!UICONTROL 访客]**&#x200B;容器。
* 报表不支持分段。
* 没有与此分段标准匹配的数据。

## 为什么我在区段管理器中看不到我创建的区段？ {#invisible}

可能的原因：

* 某些维度仅在Data Warehouse中可用，在区段管理器中不可用。
* 已指定该区段专门用于特定的报表包。
* 其他用户可能删除了共享的区段。
* 由于数据中心或浏览器缓存问题，无法加载区段。
* 未保存区段。
* 用户端可能阻止了 IP 地址。

## 为什么在应用区段后显示的数据不正确？ {#page-data}

可能的原因：

* 规则或运算符对于所需的结果不正确。
* 区段中的容器使用不正确。
* 区段使用的流量变量未经过正确设置或者已过期。
