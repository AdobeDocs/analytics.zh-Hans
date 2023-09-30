---
title: 移动设备查找维度
description: 基于设备的IP地址和用户代理的Dimension。
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 60%

---

# 移动设备查找维度

*此页面引用访问您网站的移动设备的属性。 请参阅 [移动生命周期维度](lifecycle-dimensions.md) 或 [移动生命周期量度](../metrics/lifecycle-metrics.md) 在移动设备应用程序中跟踪。*

移动设备查找 [维度](overview.md) 提供有关访问您网站的移动设备属性的洞察信息。 这些属性基于点击的用户代理和IP地址。 您可以使用这些维度来帮助了解移动设备支持哪些功能。

## 使用数据填充这些维度

这些维度引用 Adobe 内部的查找规则。

* 对于 [!UICONTROL 移动设备运营商] 维度，Adobe合作伙伴 [Digital Element](https://www.digitalelement.com/) 使用NetAcuity维护IP地址与移动运营商之间的查找服务。
* 对于所有其他移动设备维度，Adobe与 [DeviceAtlas](https://deviceatlas.com/) 在用户代理和每个相应的移动维度之间维护查找。

这些维度的可用性取决于实施类型：

* 对于AppMeasurement实施，这些维度可开箱即用。
* 对于Web SDK实施，启用 [!UICONTROL 地理查找] （适用于移动设备运营商）或 [!UICONTROL 设备查找] （对于所有其他维度），当 [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans).

## 移动设备维度描述

>[!NOTE]
>
>标有 `"None"` 的维度项目为非移动设备。如果您希望报表只包含移动设备，请将“移动设备”维度拖入 Workspace 画布的区段区域。

* **[!UICONTROL 移动设备音频支持]**：确定设备可播放的文件格式。示例值包括 `"MP3"`、`"AAC"` 和 `"MIDI Monophonic"`。此维度中的值不是相互排斥的；单次点击可以归因于多个维度项目。
* **[!UICONTROL 移动设备运营商]**：设备的电话或数据提供商。 示例值包括 `"Reliance Jio"`、`"Airtel"`、`"Vodafone"` 和 `"Verizon"`。
* **[!UICONTROL 移动设备颜色深度]**：移动设备的颜色深度（以位为单位）。
* **[!UICONTROL 移动 Cookie 支持]**：确定移动设备是否支持 Cookie。此维度不会说明浏览器是否接受Cookie。 维度项目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **[!UICONTROL 移动设备]**：访客使用的移动设备。
* **[!UICONTROL 移动设备号]**：确定移动设备是否传输其号码。此维度不提供手机号码本身。 维度项目包括 `"Supported"`、`"Not supported"` 和 `"Unknown"`。
* **[!UICONTROL 移动设备类型]**：移动设备的类型。示例值包括 `"Mobile phone"`、`"Tablet"`、`"Media player"` 和 `"Gaming console"`。
* **[!UICONTROL 移动设备DRM]**：移动设备支持的DRM类型。 示例值包括 `"DRM OMA forward"`、`"DRM OMA combined delivery"` 和 `"DRM OMA separate delivery"`。
* **[!UICONTROL 移动设备图像支持]**：移动设备支持的图像类型。 示例值包括 `"PNG"`、`"JPEG"` 和 `"GIF 87"`。此维度中的值不是相互排斥的；单次点击可以归因于多个维度项目。
* **[!UICONTROL 移动设备信息服务]**：设备支持的新闻服务类型。现代设备通常不会报告此信息。
* **[!UICONTROL 移动设备 Java 虚拟机]**：设备支持的 Java 版本。
* **[!UICONTROL 移动设备邮件修饰]**：确定设备是否支持 [德克梅](https://en.wikipedia.org/wiki/Decome)，该功能在日本设备上曾经很流行。
* **[!UICONTROL 移动设备制造商]**：按制造商对移动设备进行分类。 示例值包括 `"Apple"`、`"Samsung"`、`"Huawei"` 和 `"Motorola"`。
* **[!UICONTROL 移动设备最大书签长度]**：移动设备支持的已加入书签的 URL 最大字节数。现代设备通常没有限制。
* **[!UICONTROL 移动设备最大浏览器 URL 长度]**：移动设备支持的浏览器 URL 最大字节数。现代设备通常没有限制。
* **[!UICONTROL 移动设备最大电子邮件长度]**：移动设备支持的电子邮件最大字节数。现代设备通常没有限制。
* **[!UICONTROL 移动设备网络协议]**：设备访问互联网时支持的协议类型。示例值包括 `"EDGE"`、`"GPRS"`、`"UMTS"` 和 `"LTE"`。
* **[!UICONTROL 移动设备操作系统（已弃用）]**：请改用[操作系统](operating-systems.md)维度。
* **[!UICONTROL 移动设备一键通]**：确定设备是否支持 PTT（一键通），该功能让移动设备能够发挥类似于对讲机的作用。现代设备通常不会报告此功能。
* **[!UICONTROL 移动设备屏幕高度]**：屏幕的高度（以像素为单位）。iPhone始终报告 `"480"` 由于无法确定iPhone设备版本。 有关确定iPhone设备版本的信息，请参阅以下部分。
* **[!UICONTROL 移动设备屏幕大小]**：移动设备的完整尺寸（以像素为单位）。报告的屏幕大小不指示设备的方向。无论采用何种屏幕方向，每个设备都在报表中有固定的屏幕分辨率。此大小基于用来确定哪种方向更为可能的研究。您可能会在同一报表中看到 `"768x1024"` 和 `"1024x768"` 等大小，每种大小代表一个或多个不同的设备。
* **[!UICONTROL 移动设备屏幕宽度]**：屏幕的宽度（以像素为单位）。
* **[!UICONTROL 移动设备视频支持]**：移动设备支持的视频文件格式和编解码器。MP4 和 3GPP 文件的不同编解码器存在多个维度项目。此维度中的值不是相互排斥的；单次点击可以归因于多个维度项目。

## 按型号或版本区分 iPhone

移动设备会报告用户代理字符串中的固件版本，而非设备版本。例如，如果当代 iPhone 与上一代 iPhone 使用相同的固件版本，则二者包含相同的用户代理。由于无法使用 JavaScript 确定 iPhone 的设备版本，所有 iPhone 都属于同一存储桶。移动设备维度完全基于引用用户代理的查找，从而导致所有iPhone手机的屏幕尺寸均为 `320 x 480`.

如果要收集iPhone设备版本，有两种方法可以规避此限制。

* **使用Mobile SDK**：Mobile SDK包含展示设备版本以用于报表的维度。 与网站相比，此方法更适合于移动设备应用程序。
* **使用通过 JavaScript 提供的其他变量**：某些变量（例如 `screen.height` 和 `screen.width`）可用于推断设备版本。例如，您可以在网站上使用以下代码片断：

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  此代码块首先会检测设备是否为 iPhone。如果是，则代码会使用 JavaScript 将屏幕分辨率拉入 eVar。如果屏幕分辨率是唯一的，此方法可让您大致检测设备版本。
