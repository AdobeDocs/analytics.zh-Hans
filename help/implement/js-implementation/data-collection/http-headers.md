---
description: HTTP 请求和响应头用于收集 AppMeasurement 收集范围外的其他数据。本节介绍在数据收集过程中使用的头。
keywords: Analytics 实施
seo-description: HTTP 请求和响应头用于收集 AppMeasurement 收集范围外的其他数据。本节介绍在数据收集过程中使用的头。
seo-title: 数据收集HTTP头
solution: Analytics
title: 数据收集HTTP头
topic: 开发人员和实施
uuid: 3325e13c-b300-46e4-a592-3a83 ed59718 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 数据收集HTTP头

HTTP 请求和响应头用于收集 AppMeasurement 收集范围外的其他数据。本节介绍在数据收集过程中使用的头。

## HTTP 请求头 {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>头</b> </td> 
   <td> <b>用途</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>读取之前由我们的数据收集服务器创建的 Cookie。 </p> <p> 自 2014 年起，Adobe 服务器将弃用服务器调用所附带的所有 Cookie，但 Adobe 设置的 Cookie 除外。请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external">Experience Cloud 中使用的 Cookie</a>，获取 Adobe Cookie 的完整列表。 </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> 用于浏览器、操作系统和移动设备检测。 </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> 可作为用户代理的备用项，用于适当的浏览器，操作系统和移动设备检测，例如 OperaMini 之类的浏览器。 </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> 可作为用户代理的备用项，用于适当的浏览器，操作系统和移动设备检测，例如 OperaMini 之类的浏览器。 </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> 可作为用户代理的备用项，用于适当的浏览器，操作系统和移动设备检测，例如 OperaMini 之类的浏览器。 </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> 可作为用户代理的备用项，用于适当的浏览器，操作系统和移动设备检测，例如 OperaMini 之类的浏览器。 </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> 可作为用户代理的备用项，用于适当的浏览器，操作系统和移动设备检测，例如 OperaMini 之类的浏览器。 </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> 用作识别操作系统的备用方法。 </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> 用作客户端屏幕分辨率的备用来源。 </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> 用作客户端屏幕颜色深度的备用来源。 </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> 检测数据收集请求是否是在预获取网页的过程中发出的。 </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> 检测数据收集请求是否是在浏览器显示网页预览时发出的。 </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> 用于识别图像格式是否受浏览器支持，以便我们确定是否需要发送回一个 GIF 或 WBMP 图像。 </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> 可作为一种回退方法，用于获取有关发出数据收集请求的页面 URL 的信息（如果该请求未传递给查询字符串或不同于查询字符串中的值）。 </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> 用于查找发出数据收集请求的客户端的正确 IP 地址。此 IP 地址用于生成地理区域、移动运营商和其他报表。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>使用动态变量实现的实施可以在以上未列出的HTTP请求标头中进行读取。

## HTTP 响应头 {#section_A9C7035198C84037A21A8033CC408F0E}

| **头** | **用途** |
|---|---|
| Access-Control-Allow-Origin | 可支持向我们的服务器发出跨源资源共享形式的数据收集请求。 |
| Expires | 浏览器缓存控制。 |
| Last-Modified | 浏览器缓存控制。 |
| Cache-Control | 浏览器缓存控制。 |
| Pragma | 浏览器缓存控制。 |
| ETag | 浏览器缓存控制。 |
| Vary | 浏览器缓存控制。 |
| P3P | 提供数据收集请求的默认或自定义 P3P 策略。 |
| Status | 包含无内容请求的“SUCCESS”或“FAILURE”状态。仅在请求指定不应返回内容时使用。 |
| Reason | 包含无内容请求失败状态的原因。仅在请求指定不应返回内容时使用。 |
| Location | 用于将发出数据收集请求的客户端重定向至其他 URL。例如，我们的 Cookie 握手可检测设置访客 ID Cookie 的能力。 |
| Content-Type | 指定发送回客户端的内容类型（GIF、文本、Javascript 等）。 |
| Content-Length | 指定发送回客户端的内容大小。 |

>[!NOTE]
>
>可在响应中设置其他HTTP头以进行内部状态监视。这些头中可能会有一部分被返回到浏览器，但是浏览器并不一定需要接收它们。
