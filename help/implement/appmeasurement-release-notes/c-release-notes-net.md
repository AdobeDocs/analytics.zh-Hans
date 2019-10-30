---
description: 'null'
seo-description: 'null'
seo-title: Windows Silverlight、NET、IIS、XBOX
solution: Analytics
subtopic: 发行说明
title: Windows Silverlight、NET、IIS、XBOX
topic: 开发人员和实施
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Windows Silverlight、NET、IIS、XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>这些 SDK 已被弃用，Adobe 不再对其进行支持或分发。

> [!NOTE]要找到当前库版本，请打开调试记录。

## 版本 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

发行日期：**2014 年 8 月**

* 删除了对 [!DNL Microsoft Silverlight Analytics Framework] 的支持。Adobe 不再支持或分发 [!DNL AppMeasurement] 的 [!DNL Microsoft Silverlight Analytics Framework] 集成。

* 执行了某些内部更改以支持即将推出的功能。

## 版本 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

发行日期：**2013 年 3 月**

* 修复了在浏览器上下文以外获取 [!DNL Silverlight] 中的默认反向链接时出现异常的问题，并在 [!DNL Microsoft Silverlight Analytics Framework] 组件中正确地显示 SSL 属性。

## 版本 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

发行日期：**2013 年 2 月**

* 为了支持 Adobe 数据收集服务器中扩展的“页面 URL”字段，已添加对发送大于 255 字节 URL 的支持。大于 255 字节的页面 URL 被拆分，前面的 255 个字节显示在 `g=` 参数中，剩下的字节稍后显示在 `-g=` 查询参数的查询字符串中。这有助于在浏览器截断的情况下防止长 URL 优先于其他数据，但仍然启用对长 URL 的捕获功能。

* 添加了新的备用访客识别方法。请参阅[识别独特访客](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html)。
* 已添加可以在 `doPlugins` 内设置的新 `abort` 标记。将此标记设置为 true 会导致 [!DNL AppMeasurement] 库不继续进行跟踪呼叫。中止标记已通过每个跟踪呼叫进行重置，因此，如果还需要中止后续跟踪呼叫，则需要在 `doPlugins` 内重新设置标记。

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   这可让您将用于确认您不希望跟踪的活动的逻辑集中在一起，如一些自定义链接或显示广告中的外部链接。

## 版本 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

发行日期：**2012 年 9 月**

* 修复了可能导致在使用自定义 `media.monitor` 方法（跟踪媒体关闭事件）时未发送视频完成事件的问题。

   ```
   If(media.event=="CLOSE") { 
   … 
   } 
   ```

## 版本 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

发行日期：**2012 年 4 月**

* 添加了 [!DNL XBOX]。

## 版本 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

发行日期：**2012 年 2 月**

* [!DNL iOS] Phone 7：修复了导致 offlineThrottleDelay 无法正确应用的问题。
* 向与简易跟踪调用 (trackLight) 一起使用的变量添加了时间戳。

## 版本 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

发行日期：**2012 年 1 月**

* 使用新方法更新了视频跟踪功能，以便跟踪完成的视频查看。请参阅[在 Adobe Analytics 中测量视频](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html)。

## 版本 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* 新增对 [!DNL iOS] Phone 平台的支持与构建，包括离线跟踪。
* 支持 doRequest 委托以覆盖送出请求来跟踪数据的方式。
* 支持推动服务器端处理规则的 contextData （仅限 v15）。
* 支持简易服务器调用（目前为测试版）。
* 支持将 1 以外的值分配到事件列表中的计数器事件。
* 支持新的跟踪视频方法 - 使用转化 eVar 和事件（目前为测试版）。

