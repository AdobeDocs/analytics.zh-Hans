---
description: 了解如何排除和修复与区段相关的问题。
title: 故障排除
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 1%

---

# 故障排除

本文列出了区段的一些常见问题以及如何解决这些问题。

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## 为什么我的区段完全没有返回数据？ {#no-data}

可能的原因：

* 反向嵌套 — 例如，在![访问](/help/assets/icons/Visit.svg) **[!UICONTROL 访问]**&#x200B;容器下嵌套![用户](/help/assets/icons/User.svg) **[!UICONTROL 访客]**&#x200B;容器。
* 报表不支持分段。
* 没有与分段标准匹配的数据。

## 为什么我在区段管理器中看不到我创建的区段？ {#invisible}

可能的原因：

* 某些维度仅在Data Warehouse中可用，在区段管理器中不可用。
* 仅针对特定报表包勾选区段。
* 共享区段可能已被其他用户删除。
* 由于数据中心或浏览器缓存问题，无法加载区段。
* 区段尚未保存。
* IP地址可能在用户端被阻止。

## 为什么在应用区段后显示的数据不正确？ {#page-data}

可能的原因：

* 规则或运算符对于所需的结果不正确。
* 区段中的容器使用不正确。
* 用于划分区段的流量变量设置不正确或已过期。
