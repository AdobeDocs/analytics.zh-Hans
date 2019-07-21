---
description: 由于移动设备是通过信标进行跟踪的，因此和其他访客一样，大部分报表都是可用和正确的。
keywords: Analytics实施；报告；移动协议；搜索引擎；搜索关键字；引用域；引介；地域划分；域；连接类型；时区；cookies；java；javascript；监视颜色；显示器分辨率；浏览器宽度；高度；netscape插件
seo-description: 由于移动设备是通过信标进行跟踪的，因此和其他访客一样，大部分报表都是可用和正确的。
seo-title: 使用移动协议的设备报告
solution: Analytics
title: 使用移动协议的设备报告
topic: 开发人员和实施
uuid: aab125d-c131-4402-9bc8-1c7 fd1 bb1 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用移动协议的设备报告

由于移动设备是通过信标进行跟踪的，因此和其他访客一样，大部分报表都是可用和正确的。

可以使用 [!DNL VISTA] 更改通过移动和标准方法收集的数据。支持所有[!UICONTROL 自定义][!UICONTROL 分析]（[!UICONTROL prop] 和 [!UICONTROL eVar]）、[!UICONTROL 事件]、[!UICONTROL 网站流量]和[!UICONTROL 路径分析]报表。

## 搜索引擎、搜索关键词、反向链接域名和反向链接 {#section_184D2EF9D906443FBDED04A09CDC50E9}

只有在从移动页面发送的图像请求中填充了反向链接时，这些报表才会有数据。按照“在不使用 JavaScript 的情况下实施”白皮书中所述，反向链接通过“r”查询字符串参数填充。还必须手动将反向链接信息传递到图像请求中。

“r”查询字符串参数必须包含反向链接协议。如果不使用协议，则不会填充反向链接报表。`r=https://msn.com``r=msn.com`例如，不使用。

## 地域划分和域名 {#section_2B4E9443AAFE4ECA961F9E993592E628}

地域划分报表基于发送请求的设备的 IP 地址。因为移动设备依赖网关来请求 Adobe 服务器中的图像，因此使用网关的 IP 地址确定用户的地域位置。由于网关及其 IP 地址都是为大型网络注册的，因此关联的地域位置通常不是很准确。

域名也基于网关的 IP 地址，这意味着域名报表通常会包含拥有网关的运营商名称。由于移动虚拟网络运营商 (MVNO) 原因，这可能不准确。

## 连接类型 {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe 维护着一系列属于移动运营商的已知 IP 地址。当收到的点击来自属于已知移动运营商的 IP 范围时，该点击在“连接类型报表”上会显示为“移动运营商”。否则，移动流量会列在“Lan/Wifi”下面。

## 时区、Cookie、Java、JavaScript、显示器颜色和分辨率、浏览器宽度和高度以及 Netscape 插件 {#section_158C848273AE4691B4413767E849E846}

这些报表都是通过使用 JavaScript 检测浏览器的特定设置来收集的。由于在移动设备上不是使用 JavaScript 来创建图像信标的，因此这些报表不包含从移动用户收集的数据。
