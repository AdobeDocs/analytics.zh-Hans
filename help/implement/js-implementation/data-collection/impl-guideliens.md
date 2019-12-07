---
description: 以下是使用相同 Cookie 域的实施指南，由此可以跟踪不同类型实施之间的访问。
keywords: Analytics Implementation
title: 实施指南
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 实施指南

以下是使用相同 Cookie 域的实施指南，由此可以跟踪不同类型实施之间的访问。

* **RSID：**[!UICONTROL 报表包 ID]
* **VNS：**&#x200B;即 Visitor name space（访客命名空间），是用于存储[!DNL 2o7.net]访客 ID Cookie 的 [!DNL omtrdc.net] 或  的子域。
* **COOKIEDOMAIN：**&#x200B;您的 VNS + trackingServer。根据您的数据中心和 RDC 配置的不同，这些域名会有很大区别。[如果您不确定您的数据收集域](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) ，请与客户服务部门联系。

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## 硬编码图像请求

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

如果使用第一方 Cookie 实施，则 `VNS.COOKIEDOMAIN.net` 可被所用的第一方 Cookie 域名替换。例如，`adobe.com` 上的第一方 Cookie 将被类似于 `metrics.adobe.com` 的域名替换。
