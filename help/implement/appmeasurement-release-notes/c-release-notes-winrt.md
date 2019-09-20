---
description: 'null'
seo-description: 'null'
seo-title: WinRT for Windows 8
solution: Analytics,Experience Cloud
subtopic: 发行说明
title: WinRT for Windows 8
topic: 开发人员和实施
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# WinRT for Windows 8{#winrt-for-windows}

>[!NOTE]
>
>要查找当前库版本，请打开调试日志记录。

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL WinRT] for [!DNL Windows] 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) SDK. 未来不会再对此 SDK 进行进一步的研发。

## 4.0 版 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

发行日期：**2014 年 6 月 17 日**

新版本的新增功能包括地理位置、生命周期值、定时操作和启用支持。

## 版本 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

发行日期：**2014 年 5 月 22 日**

错误修复和性能改进。

## 版本 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

发行日期：**2013 年 10 月 17 日**

* [!DNL Windows] 8.1兼容性

## 版本 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

发行日期：**2013 年 4 月 18 日**

* 修复了导致上一会话长度有时计算错误的问题。

## 版本 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

发行日期：**2013 年 3 月 21 日**

* `ADMS_Measurement.visitorID` 现在会预填充默认值。
* 修复了检索设备信息时存在的一个问题。

## 版本 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

发行日期：**2013 年 2 月 21 日**

* 已弃用 `offlineThrottleDelay`，因为优化线程后不再需要此设置。为保持向后兼容性，此设置仍然存在，但不再具有任何效果。
* `DayOfWeek` 现在从星期日开始计数，以 1 天为单位，以匹配在其他平台上收集的值。
* 在 TrackingHelper.js 中添加了事件侦听器自动订阅功能，以简化生命周期跟踪。

## 版本 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

发行日期：**2012 年 11 月**

* 现在可针对 C#、C++ 和 HTML5/WinJS 平台准确地收集屏幕分辨率。
* `ADMS_Churn` 类现在为内部类。 要使用最佳实践来进行应用程序生命周期跟踪，请使用以下调用：

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. 如果注册的会话长度超过了最大限制，则将发送您的最大会话长度。Default `maxSessionLength` is 3600 (seconds).
* 新增的 `lifecycleSessionTimeout` 配置变量能让您指定在将应用程序启动视为新会话之前，应用程序启动必须经过的时间长度（秒）。
* 生命周期量度中新增了“上一会话时长”量度。
* 为清楚起见，更新了 TrackingHelper。
* 修复了媒体模块错误。

## 版本 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**2012 年 10 月 日**

第一版。
