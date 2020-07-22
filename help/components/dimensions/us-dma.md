---
title: 美国 DMA
description: 受冲击的指定市场区域。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---


# 美国 DMA

“美国DMA”维度报告访客的指定市场区域(DMA)。 它基于尼尔森汇编的媒体 [市场](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/)。

## 用数据填充此维

此维引用Adobe内部的查找规则。 查找值基于随点击发送的IP地址。 Adobe与Nielsen合作，维护IP地址与DMA之间的查找。 此维度适用于所有实施。

>[!TIP]
>
>如果您的组织遵循严格的隐 [私法规，而模糊](/help/admin/admin/general-acct-settings-admin.md) 化IP地址是不够的，您可以请求完全禁用地理位置数据。 使用报表包ID联系客户关怀，并请求关闭报表包的“地理位置”。

## 维项

维项包括访客的DMA和DMA代码。 3位数的代码不是邮政编码，而是尼尔森的DMA代码。 示例值 `"Dallas-Ft. Worth (623)"`包括 `"New York (501)"`、或 `"Los Angeles (803)"`。 维项目包 `"No Metro (0)"` 括美国以外的所有国际流量。

## 报告位置与实际位置之间的差异

由于此维度基于IP地址，因此某些情况可能显示报告位置与实际位置之间的差异：

* **代表公司代理的IP地址**: 这些访客可以显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动IP地址**: 移动IP定位工作的级别因位置和网络而异。 许多运营商通过集中或区域存在点回传IP流量。
* **卫星ISP用户**: 识别这些用户的特定位置是困难的，因为他们通常看起来源自上行链路位置。
* **军事和政府知识产权**: 代表在全球各地旅行并通过其家乡（而不是他们目前驻在的基地或办公室）进入的人员。
