---
title: 国家/地区
description: 点击源自的国家/地区。
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 60%

---

# 国家/地区

“国家/地区”[维度](overview.md)报告点击源自的国家/地区。 此维度可帮助确定访客在访问您的网站时最有可能所在的国家/地区。您可以利用这些数据专注于这些国家/地区的营销工作，或确保在使用不同主要语言的国家/地区提供最佳的网站体验。

## 使用数据填充此维度

此维度引用 Adobe 内部的查找规则。查找值基于随点击发送的 IP 地址。Adobe与[Digital Element](https://www.digitalelement.com/)合作，以维护IP地址与国家/地区之间的查找服务。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)时启用[!UICONTROL 地理查找]。

## 维度项目

维度项目包括全世界的各个国家/地区。示例值包括 `"United States"`、`"United Kingdom"` 或 `"India"`。

## 报告位置与实际位置之间的差异

由于此维度基于 IP 地址，因此某些情况可能显示报告位置与实际位置之间存在差异：

* **代表公司代理的 IP 地址**：这些访客可能会显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动设备 IP 地址**：移动设备 IP 定位会根据不同位置和网络以不同级别运行。某些运营商通过集中式或区域式接入点回传IP流量。
* **卫星 ISP 用户**：确定这些用户的特定位置比较困难，因为他们通常看起来源自上行链路位置。
* **军事和政府 IP**：表示全球各地的差旅人员通过其本地地址进入，而非他们目前驻扎的基地或办公室。
* **出于隐私原因而遮蔽IP地址的代理**：Apple的私有中继等服务通过中间或代理随机发送数据来隐藏真实的IP地址。 然后，此代理在转发到Adobe之前替换其他IP地址。
