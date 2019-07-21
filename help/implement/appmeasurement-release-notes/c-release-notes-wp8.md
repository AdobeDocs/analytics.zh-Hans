---
description: 'null'
seo-description: 'null'
seo-title: Windows Phone 8
solution: Analytics，Marketing Cloud
subtopic: 发行说明
title: Windows Phone 8
topic: 开发人员和实施
uuid: 7378969a-d219-42bf-9750-141acc9 e4 b7 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>要查找当前的库版本，请开启调试日志。

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>[!DNL Windows] 电话SDK被Windows8.1通用App [Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK取代。未来不会再对此 SDK 进行进一步的研发。

## 版本 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

发行日期：**2013 年 8 月 21 日**

* 上下文数据键现在允许使用下划线。

## 版本 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

发行日期：**2013 年 5 月 22 日**

* 错误修复和性能改进。

## 版本 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

发行日期：**2013 年 4 月 18 日**

* 修复了导致上一会话长度有时计算错误的问题。

## 版本 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

发行日期：**2013 年 3 月 21 日**

* 修复了 `DateTime` 对象存在的本地化问题。

## 版本 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

发行日期：**2013 年 2 月 26 日**

* `ADMS_Measurement.visitorID` 现在预填充默认值。
* 修复了有时会导致缓存自动响应的问题。

## 版本 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

发行日期：**2013 年 2 月 21 日**

* 已弃用 `offlineThrottleDelay`，因为优化线程后不再需要此设置。为保持向后兼容性，此设置仍然存在，但不再具有任何效果。
* `DayOfWeek` 现在从星期日开始计数，以 1 天为单位，以匹配在其他平台上收集的值。
* 修复了离线存储有时导致应用程序崩溃的问题。

