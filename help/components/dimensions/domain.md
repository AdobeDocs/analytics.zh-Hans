---
title: 域
description: 访客用来访问 Internet 的组织或 ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 52%

---

# 域

“域”[维度](overview.md)报告访客用于访问Internet的访问点。

## 使用数据填充此维度

Adobe 合作伙伴使用 [Digital Element](https://www.digitalelement.com/) 确定访问点域。有包括 DNS 反向查询在内的多种方法可用于确定访问点域。它不需要任何配置，也没有要填充的变量。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)时启用[!UICONTROL 网络查找]。

## 维度项目

维度项目示例包括 `comcast.net`、`rr.com`、`sbcglobal.net` 和 `amazonaws.com`。这些域是接入点，不一定是代表ISP或组织的域。

维度值 `None` 意味着访问点 IP 地址的所有者没有提供域。
