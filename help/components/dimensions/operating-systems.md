---
title: 操作系统
description: 访客的操作系统。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 17c441f8855b8ca0604076763817de8d4d3b8efb
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 34%

---

# 操作系统

“操作系统”维度显示访客使用的操作系统和版本。如果您的 Web 资产上具有特定于操作系统的功能，则此维度可以帮助您了解最常用的操作系统。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

## 维度项目

维度项目包括访客使用的操作系统。示例包括 `"Windows 10"`、`"OS X 10.15"` 和 `"Android 9"`。

## 标签和定义中的更改

以下是有关操作系统如何在用户代理和Adobe Analytics报表中显示的特定问题列表。

### 更改了Apple操作系统的命名约定：

从版本11开始，我们将使用MacOS而不是OS X来引用Apple操作系统。

示例：

* “OS X 10.15”(请参阅下面关于版本10.15.7的注释，以了解UA字符串的表示形式)。
* &quot;MacOS 11.0.0

### Mac OS版本10.15.7之后，用户代理中的版本不正确 

Apple计算机上的用户代理将操作系统版本显示为10.15.7，即使它是较新版本。 这样做是因为在UA中包含版本11显然导致了某些网站的问题。 对于 *所有浏览器* 和与Google在Chromium浏览器上的用户代理的“冻结”无关。

请注意，客户端提示在平台版本提示(“Sec-CH-UA-Platform-Version”)中包含正确的版本。 这是一个高熵提示，因此不会由Adobe自动收集。 请参阅 [Adobe Analytics提示常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 以了解有关如何收集高熵提示的详细信息。

### 从Windows 11开始，用户代理中的Windows版本不正确

自2023年1月起，所有浏览器中的用户代理都将Windows 11表示为Windows 10。

请注意，客户端提示在平台版本提示(“Sec-CH-UA-Platform-Version”)中包含正确的版本。 这是一个高熵提示，因此不会由Adobe自动收集。 请参阅 [Adobe Analytics提示常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 以了解有关如何收集高熵提示的详细信息。
