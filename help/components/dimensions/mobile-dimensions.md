---
title: 移动维度
description: 基于设备的用户代理字符串的维度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 4%

---


# 移动维度

*本页引用访问您网站的移动设备的属性。 如果要跟踪移动应用程序上的设备，请参阅[实施用户指南中](/help/implement/mobile-device-sdk.md)的实施移动设备Analytics。*

移动维度提供有关访问网站的移动设备属性的洞察。 您可以使用这些维度来帮助了解移动设备支持哪些功能。

## 用数据填充这些维

这些维引用Adobe内部的查找规则。 查找值基于随点击 `User-Agent` 发送的HTTP头。 Adobe与DeviceAtlas [合作](https://deviceatlas.com/) ，维护用户代理和移动维度之间的查找。 如果您使用AppMeasurement库(如通过Adobe Experience Platform启动)，所有移动维度都将开箱即用。

## 移动维度描述

>[!NOTE]
>
>标记为非 `"None"` 移动设备的维度项目。 如果您希望报告只包含移动设备，请将“移动设备”维度拖入Workspace画布的区段区域。

* **移动音频支持**: 确定设备可播放的文件格式。 示例值 `"MP3"`包括 `"AAC"`、和 `"MIDI Monophonic"`。 此维中的值不是互斥的； 单次点击可归因于多个维度项。
* **移动运营商**: 如果用户代理包含运营商专用设备，则运营商是维度项。 示例值 `"Reliance Jio"`包括 `"Airtel"`、 `"Vodafone"`、和 `"Verizon"`。
* **移动颜色深度**: 移动设备的色深（以位为单位）。
* **移动cookie支持**: 确定移动设备是否支持Cookie。 如果浏览器接受cookie，则此报告不声明。 维项目 `"Supported"`包括 `"Not supported"`、和 `"Unknown"`。
* **移动设备**: 访客使用的移动设备。
* **移动设备号**: 确定移动设备是否传输其号码。 维项目 `"Supported"`包括 `"Not supported"`、和 `"Unknown"`。
* **移动设备类型**: 移动设备的类型。 示例值 `"Mobile phone"`包括 `"Tablet"`、 `"Media player"`、和 `"Gaming console"`。
* **移动DRM**: 移动设备支持的DRM类型。 示例值 `"DRM OMA forward"`包括 `"DRM OMA combined delivery"`、和 `"DRM OMA separate delivery"`。
* **移动图像支持**: 移动设备支持的图像类型。 示例值 `"PNG"`包括 `"JPEG"`、和 `"GIF 87"`。 此维中的值不是互斥的； 单次点击可归因于多个维度项。
* **移动信息服务**: 设备支持的新闻服务类型。 近期设备通常不会报告此信息。
* **移动Java VM**: 设备支持的Java版本。
* **移动邮件装饰**: 确定设备是否支持反编译，该功能在日文设备上曾经很流行。
* **移动制造商**: 按制造商对移动设备进行分组。 示例值 `"Apple"`包括 `"Samsung"`、 `"Huawei"`、和 `"Motorola"`。
* **移动最大书签长度**: 移动设备在已加入书签的URL中支持的最大字节数。 最近的设备通常没有限制。
* **移动设备最大浏览器URL长度**: 移动设备在URL中支持的最大字节数。 最近的设备通常没有限制。
* **移动设备最大电子邮件长度**: 移动设备在电子邮件中支持的最大字节数。 最近的设备通常没有限制。
* **移动网络协议**: 设备访问Internet时支持的协议类型。 示例值 `"EDGE"`包括 `"GPRS"`、 `"UMTS"`、和 `"LTE"`。
* **移动操作系统（已弃用）**: 请改 [用操作系统](operating-systems.md) 维。
* **移动即说**: 确定设备是否支持PTT（即按即说），这允许移动设备的行为类似于双向无线电。 近期设备通常不报告此功能。
* **移动屏幕高度**: 屏幕高度（以像素为单位）。 请注意，由于无法确 `"480"` 定iPhone设备版本，iPhone始终会报告。 请参阅下面有关确定iPhone设备版本的部分。
* **移动屏幕大小**: 移动设备的完整尺寸（以像素为单位）。 报告的屏幕大小不指示设备的方向。无论采用何种屏幕方向，每个设备都在报表中有固定的屏幕分辨率。此大小基于用来确定哪种方向更为可能的研究。You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **移动屏幕宽度**: 屏幕的宽度（以像素为单位）。
* **移动视频支持**: 移动设备支持的视频文件格式和编解码器。 MP4和3GPP文件的不同编解码器存在若干维项。 此维中的值不是互斥的； 单次点击可归因于多个维度项。

## 按型号或版本分离iPhone

移动设备在用户代理字符串中报告其固件版本，而不是设备版本。 例如，当前代iPhone包含与上一代iPhone相同的用户代理（如果它们使用相同的固件版本）。 由于无法使用JavaScript确定iPhone的设备版本，所有iPhone都属于同一存储桶。 手机尺寸严格地基于引用用户代理的查找，因此您会发现所有iPhone都报告手机屏幕尺寸为 `320 x 480`。

如果要收集iPhone设备版本，有两种方法可以规避此限制。

* **使用iOS SDK**: 移动SDK包含展示设备版本以用于报告的维。 与网站相比，此方法更适合于移动应用程序。
* **使用通过JavaScript提供的其他变量**: 某些变量(如 `screen.height` 和 `screen.width`)可用于推断设备版本。 例如，您可以在站点上使用以下代码片断：

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   此代码块首先检测设备是否为iPhone。 如果是，则代码使用JavaScript将屏幕分辨率拉入eVar。 如果屏幕分辨率是唯一的，此方法允许您大致检测设备版本。
