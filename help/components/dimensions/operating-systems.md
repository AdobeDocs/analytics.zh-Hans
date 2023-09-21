---
title: 操作系统
description: 访客的操作系统。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 26%

---

# 操作系统

“操作系统” [维度](overview.md) 显示访客使用的操作系统和版本。 如果您的 Web 资产上具有特定于操作系统的功能，则此维度可以帮助您了解最常用的操作系统。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。查找值基于图像请求中的 `User-Agent` HTTP 标头。如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。

## 维度项目

维度项目包括访客使用的操作系统。示例包括 `"Windows 10"`、`"OS X 10.15"` 和 `"Android 9"`。

## 标签和定义的更改

以下列出了有关操作系统在用户代理和Adobe Analytics报表中的呈现方式的具体问题。

### 更改操作系统的粒度

于2023年3月2日，我们更新了报告，以纳入有关操作系统的更多详情。 在此日期之后，我们将提供操作系统修补程序版本。 例如，使用OS X 10.15.7的用户在3月2日之前显示为“OS X 10.15”。 3月2日之后，它们将显示为“OS X 10.15.7”。

### 更改Apple操作系统的命名约定：

从版本11开始，我们将使用MacOS而不是OS X来引用Apple操作系统。

示例：

* “OS X 10.15”（请参阅下面关于10.15.7版的UA字符串表示法的说明）。
* “MacOS 11.0.0

### Mac OS版本10.15.7之后的用户代理中的版本不正确 

即使对于较新版本，Apple计算机上的用户代理也会将操作系统版本显示为10.15.7。 之所以这样做，是因为在UA中包括版本11显然导致某些网站出现问题。 这适用于 *所有浏览器* 与Google在Chromium浏览器上“冻结”用户代理无关。

请注意，客户端提示在平台版本提示中包含正确的版本(“Sec-CH-UA-Platform-Version”)。 这是一个高熵提示，因此Adobe不会自动收集它。 请参阅 [Adobe Analytics提示常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 了解有关如何收集高熵提示的详细信息。

### 从Windows 11开始的用户代理中的Windows版本不正确

截至2023年1月，所有浏览器中的用户代理都显示Windows 11为Windows 10。

请注意，客户端提示在平台版本提示中包含正确的版本(“Sec-CH-UA-Platform-Version”)。 这是一个高熵提示，因此Adobe不会自动收集它。 请参阅 [Adobe Analytics提示常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 了解有关如何收集高熵提示的详细信息。
