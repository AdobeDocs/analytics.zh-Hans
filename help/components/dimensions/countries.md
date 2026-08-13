---
title: 国家/地区
description: 点击源自的国家/地区。
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
TQID: https://experienceleague.adobe.com/qEG8tKa7eEuYV6XgYSlf4Y8FPaCiyWxPmdtL6KkKm94
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 65%

---

# 国家/地区

“国家/地区”[维度](overview.md)报告点击源自的国家/地区。 此维度可帮助确定访客在访问您的网站时最有可能所在的国家/地区。 您可以利用这些数据专注于这些国家/地区的营销工作，或确保在使用不同主要语言的国家/地区提供最佳的网站体验。

## 使用数据填充此维度

此维度引用 Adobe 内部的查找规则。 查找值基于随点击发送的 IP 地址。 Adobe 与 [Digital Element](https://www.digitalelement.com/) 合作，共同维护 IP 地址与国家/地区之间的查找服务。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)时启用[!UICONTROL 地理查找]。

## 维度项目

维度项目包括全世界的各个国家/地区。 示例值包括 `"United States"`、`"United Kingdom"` 或 `"India"`。

## 报告位置与实际位置之间的差异

由于此维度基于 IP 地址，因此某些情况可能显示报告位置与实际位置之间存在差异：

* **代表公司代理的 IP 地址**：这些访客可能会显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动设备 IP 地址**：移动设备 IP 定位会根据不同位置和网络以不同级别运行。 某些运营商通过集中式或区域式接入点回传IP流量。
* **卫星 ISP 用户**：确定这些用户的特定位置比较困难，因为他们通常看起来源自上行链路位置。
* **军事和政府 IP**：表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。
* **出于隐私原因而遮蔽IP地址的代理**：Apple的私有中继等服务通过中间或代理随机发送数据来隐藏真实的IP地址。 然后，此代理会替换其他IP地址，然后再转发到Adobe。
