---
description: 说明如何在 HTML 示例页面中使用服务器生成的图像标记的示例。
keywords: Analytics 实施;变量
seo-description: 说明如何在 HTML 示例页面中使用服务器生成的图像标记的示例。
seo-title: 示例代码
solution: Analytics
title: 示例代码
topic: 开发人员和实施
uuid: 47e5e82c-cfb2-4912-919b-720b2ee852ba
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 示例代码

说明如何在 HTML 示例页面中使用服务器生成的图像标记的示例。

下表显示在示例中使用的值。

| 变量 | 值 |
|---|---|
| pageName | 订单确认 |
| 当前 URL | https://www.somesite.com/cart/confirmation.asp |
| events | purchase,event1 |
| c1 | 已注册 |
| purchaseID | 0123456 |
| 产品 | Books;Book Name;1;19.95 |
| state | CA |
| zip | 90210 |
| 随机 # | 123456 |

## 示例 1 {#section_91D91CE318AE43F0ADDF6005607E83C7}

以下示例显示服务器端图像标记。突出显示的随机数可防止将图像放入缓存。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<img src="https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS 
<codeph outputclass="syntax">
  /123456?pageName=Order%20 Confirmation&events=purchase%2Cevent1&c1=Registered&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=https%3A//www.somesite.com/cart/confirmation.asp" width="1" height="1" border="0" /> 
 </body> 
 </html> 
  
</codeph outputclass="syntax">
```

## 示例 2 {#section_726D12029583428BA853043F988ED1B8}

以下示例显示最小的 JavaScript 图像标记。

```
<html> 
<head> 
</head> 
<body> 
Order Confirmation<br> 
Thanks for your order #0123456.
<script language="javascript"><!— 
s.s_date = new Date(); 
s.s_rdm = s.s_date.getTime(); 
s.s_desturl="<img width=\"1\" height=\"1\" 
src=\"https://102.112.207.net/b/ss/suite1,suite2/1/G.4--NS/" + s.s_rdm + 
"?pageName=Order%20Confirmation&events=purchase%2Cevent1&c1=Registered 
&purchaseID=0123456&products=Books%3BBook%20Name%3B1%3B19.95&state=CA&zip=90210&g=http 
s%3A//www.somesite.com/cart/confirmation.asp\">"; 
document.write(s.s_desturl); 
//--></script> 
</body> 
</html> 
```

