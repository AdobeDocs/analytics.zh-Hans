---
description: 以 adobe.com 为例，这里介绍的实施引用了相同的 visid Cookie。
keywords: Analytics 实施
seo-description: 以 adobe.com 为例，这里介绍的实施引用了相同的 visid Cookie。
seo-title: 实施示例
solution: Analytics
title: 实施示例
topic: 开发人员和实施
uuid: 17d8d2b2-2303-495a-b0 f9-d8 d3 c05 f3893
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 实施示例

以 adobe.com 为例，这里介绍的实施引用了相同的 visid Cookie。

**Javascript：**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**硬编码图像请求：**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**Appmeasurement：**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

当利用第一方 Cookie 时：

**Javascript：**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**硬编码图像请求：**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement：**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

