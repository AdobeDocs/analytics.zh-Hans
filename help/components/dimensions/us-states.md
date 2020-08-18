---
title: 美国各州
description: 访客所在的美国州。
translation-type: tm+mt
source-git-commit: fdc77997c8aea07cc7db1d06c5c0c2cd2f2abbd9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 79%

---


# 美国州

“美国州”维度报告访客在美国的哪个州。它与[地区](regions.md)维度相似，只是该维度特定于美国。如果您希望获得比[国家/地区](countries.md)更精细，同时又不如[城市](cities.md)那么精细的洞察信息，使用此维度很有价值。

## 使用数据填充此维度

此维度引用 Adobe 内部的查找规则。查找值基于随点击发送的 IP 地址。Adobe 与 [Digital Element](https://www.digitalelement.com/) 合作，共同维护 IP 地址与国家/地区之间的查找服务。此维度可开箱即用于所有实施。

>[!TIP]
>
>如果您的组织遵循严格的隐私法规，但[模糊处理 IP 地址](/help/admin/admin/general-acct-settings-admin.md)力度不够，则可以请求完全禁用地理位置数据。使用报表包 ID 联系客户关怀，并请求关闭报表包的“地理位置”。

## Dimension项

Dimension项包括区域所在的地区和国家。 示例值包括 `"California"`、`"Texas"` 或 `"Virginia"`。The dimension item `"Unspecified"` includes all international traffic outside of the United States.

此维度可 `"AOL"`以包括拨号Internet服务提供商。 为此服务的订阅者分配一个接入点。 AOL用户使用此接入点的IP地址。 由于此维度基于IP地址，因此使用接入点的地理位置而不是访客的实际位置。

## 报告位置与实际位置之间的差异

由于此维度基于 IP 地址，因此某些情况可能显示报告位置与实际位置之间存在差异：

* **代表公司代理的 IP 地址**：这些访客可能会显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动设备 IP 地址**：移动设备 IP 定位会根据不同位置和网络以不同级别运行。许多运营商通过集中式或区域式接入点回传 IP 流量。
* **卫星 ISP 用户**：确定这些用户的特定位置比较困难，因为他们通常看起来源自上行链路位置。
* **军事和政府 IP**：表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。
