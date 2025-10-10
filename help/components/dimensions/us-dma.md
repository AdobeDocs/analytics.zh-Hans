---
title: 美国 DMA
description: 点击的指定市场区域。
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 64%

---

# 美国 DMA

“美国DMA”[维度](overview.md)报告访客的指定市场区域(DMA)。 它基于 [Nielsen](https://www.nielsen.com/dma-regions/) 编辑的媒体市场。

## 使用数据填充此维度

此维度引用 Adobe 内部的查找规则。查找值基于随点击发送的 IP 地址。Adobe与Nielsen合作，共同维护IP地址与DMA之间的查找服务。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[!UICONTROL 配置数据流]时启用[地理查找](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)。

## 维度项

Dimension项目包括访客的DMA和DMA代码。 3 位数的代码不是邮政编码，而是 Nielsen 的 DMA 代码。示例值包括 `"Dallas-Ft. Worth (623)"`、`"New York (501)"` 或 `"Los Angeles (803)"`。维度项目 `"No Metro (0)"` 包括美国以外的所有国际流量。

## 报告位置与实际位置之间的差异

由于此维度基于 IP 地址，因此某些情况可能显示报告位置与实际位置之间存在差异：

* **代表公司代理的 IP 地址**：这些访客可能会显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动设备 IP 地址**：移动设备 IP 定位会根据不同位置和网络以不同级别运行。某些运营商通过集中式或区域式接入点回传IP流量。
* **卫星 ISP 用户**：确定这些用户的特定位置比较困难，因为他们通常看起来源自上行链路位置。
* **军事和政府 IP**：表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。
* **出于隐私原因而遮蔽IP地址的代理**：Apple的私有中继等服务通过中间或代理随机发送数据来隐藏真实的IP地址。 然后，此代理会替换其他IP地址，然后再转发到Adobe。
