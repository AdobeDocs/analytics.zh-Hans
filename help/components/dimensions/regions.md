---
title: 地区
description: 访客的地理区域。
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
TQID: https://experienceleague.adobe.com/Yjy-VGZ0alwfMR408QClnOEIB2z-rfgH5XCn9K0bE1A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 87%

---

# 地区

“区域”[维度](overview.md)报告访客的地理区域。 它是比国家小但比城市大的地理区域。 在某些国家，区域是一个州、省或专区。 在其他地区，它是一个成员国、辖区或大都市区域。 如果您希望获得比[国家/地区](countries.md)更精细，同时又不如[城市](cities.md)那么精细的洞察信息，使用此维度很有价值。

## 使用数据填充此维度

此维度引用 Adobe 内部的查找规则。 查找值基于随点击发送的 IP 地址。 Adobe 与 [Digital Element](https://www.digitalelement.com/) 合作，共同维护 IP 地址与国家/地区之间的查找服务。 此维度可开箱即用于所有实施。

## 维度项目

维度项包括地区以及该地区所在的国家/地区。 示例值包括 `"California (United States)"`、`"Tokyo (Japan)"` 或 `"Sao Paulo (Brazil)"`。

某些维度项可能包括 `"AOL"`，它是一个拨号上网服务提供商。 此服务的订阅者会根据其建立帐号的国家/地区来分配一个接入点。 AOL 用户将使用此接入点的 IP 地址。 由于此维度基于 IP 地址，因此会使用接入点的地理位置，而不是访客的实际位置。

## 报告位置与实际位置之间的差异

由于此维度基于 IP 地址，因此某些情况可能显示报告位置与实际位置之间存在差异：

* **代表公司代理的 IP 地址**：这些访客可能会显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动设备 IP 地址**：移动设备 IP 定位会根据不同位置和网络以不同级别运行。 许多运营商通过集中式或区域式接入点回传 IP 流量。
* **卫星 ISP 用户**：确定这些用户的特定位置比较困难，因为他们通常看起来源自上行链路位置。
* **军事和政府 IP**：表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。
* **出于隐私原因而遮蔽IP地址的代理**：Apple的私有中继等服务通过中间或代理随机发送数据来隐藏真实的IP地址。 然后，此代理会替换其他IP地址，然后再转发到Adobe。
