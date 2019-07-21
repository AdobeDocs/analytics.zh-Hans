---
description: s.t() 函数可将页面上定义的所有变量编译到一个图像请求中，并将其发送到我们的服务器。
keywords: 跟踪；Analytics实施；页面跟踪；跟踪页面
seo-description: s.t() 函数可将页面上定义的所有变量编译到一个图像请求中，并将其发送到我们的服务器。
seo-title: s.t() 函数 - 页面跟踪
solution: Analytics
subtopic: 函数
title: s.t() 函数 - 页面跟踪
topic: 开发人员和实施
uuid: 67696e46-1e0d-4200-bfad-417d1023948
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.t() 函数 - 页面跟踪

s.t() 函数可将页面上定义的所有变量编译到一个图像请求中，并将其发送到我们的服务器。

## 函数的属性 {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* 删除 [!UICONTROL s.t()] 调用可防止任何数据抵达 [!DNL Analytics]。多个 [!UICONTROL s.t()] 调用会触发多个图像请求（使网站上报告的流量加倍）。

* 如果您希望在单个页面加载时触发多个图像请求，则推荐使用 [!UICONTROL s.tl()] 函数。
* 触发此函数将一直增加[!UICONTROL 页面查看次数]并始终包含 [!UICONTROL s.pageName] 变量。

## 实施 {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

在[!UICONTROL 代码管理器]内生成代码之后，您将在页面代码的底部获得以下信息：

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

每个代码行都具有特定目的：

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

正是此代码行触发了 Javascript 函数。[!UICONTROL s_code] 变量及其伴随的 document.write 方法适用于不支持图像对象的浏览器（版本 3 之前的 Netscape 浏览器和版本 4 之前的 Internet Explorer；其使用人数占所有互联网用户的比例预计不超过 5%）。

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

有关 [!UICONTROL s.t()] 函数的其他问题，请联系贵组织的帐户管理员。他们将安排您与 Adobe 实施顾问进行会谈，以便为您提供帮助。
