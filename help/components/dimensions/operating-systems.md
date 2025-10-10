---
title: 操作系统
description: 访客的操作系统。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# 操作系统

“操作系统”[维度](overview.md)显示访客使用的操作系统和版本。 如果您的 Web 资产上具有特定于操作系统的功能，则此维度可以帮助您了解最常用的操作系统。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，共同在用户代理和操作系统之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[!UICONTROL 配置数据流]时启用[设备查找](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans)。

## 维度项目

维度项目包括访客使用的操作系统。示例包括 `"Windows 10"`、`"OS X 10.15.7"` 和 `"Android 9"`。

## 跟踪准确的操作系统版本

随着行业转向客户端提示，一些操作系统版本可能会出现混淆。 例如，如果您不收集高熵客户端提示，“Windows 10”和“Windows 11”都可以分组到“Windows 10”下。 有关详细信息，请参阅技术说明指南中的[客户端提示](/help/technotes/client-hints.md)。
