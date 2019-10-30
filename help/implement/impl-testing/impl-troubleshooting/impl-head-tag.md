---
description: Analytics 代码创建一个图像对象，它是一个不会显示在页面上的非可视图像。
keywords: Analytics 实施
seo-description: Analytics 代码创建一个图像对象，它是一个不会显示在页面上的非可视图像。
seo-title: 在 Head 标记中置入 Analytics 代码
solution: Analytics
title: 在 Head 标记中置入 Analytics 代码
topic: 开发人员和实施
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 在 Head 标记中置入 Analytics 代码

Analytics 代码创建一个图像对象，它是一个不会显示在页面上的非可视图像。

> [!NOTE]本节仅适用于旧版 s_code.js 实施。[AppMeasurement for JavaScript 1.0](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 支持在 `<head>` 标记中部署库和页面代码。

之前，常见的实施做法是在 <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> 和 </head> 标记之间置入 Analytics JavaScript 代码。将代码置于这些标记之间，可防止由发送数据至 Adobe 服务器的请求返回的 1 x 1 像素图像以任何方式影响页面布局。将代码置于文件头中可使代码更早显示。这样，它可以更快执行，从而允许您更有效地计算部分页面加载的页面查看次数。

某些代码元素需要有 body 对象的存在。由于 Web 浏览器是以代码的接收顺序执行这些代码，那么如果 Analytics JavaScript 代码位于文件头中，则它会在 body 对象存在之前执行。结果，您的实施不会收集 [!UICONTROL ClickMap] 数据，并且文件下载或[!UICONTROL 退出]链接的自动跟踪不可用。您也不会收到连接类型或访客主页数据。将代码置于文件头中是可行的，但结果却只能得到极其有限的 Analytics 版本，用户可能很想知道为什么某些报表和工具（包括 [!UICONTROL ClickMap]）没有记录数据。

Analytics 代码可以置于格式良好的 HTML 页面的 BODY 标记 (<BODY></BODY>) 内的任意位置。Adobe 建议将代码置于页面顶部的全局包含文件中（在 HTML body 标记内）。除以下特别说明之外，代码可以置于页面的任何位置：

* 如果要将代码置于表格内，则必须仅将该代码放在 <td></td> 标记内。例如，不要将代码置于开始 <tr> 标记和开始 <td> 标记之间。
* 设置变量的代码必须在 s_code.js 文件的引用之后发生。
* 确保 s_code.js 文件中 *`s_account`* 变量中的[!UICONTROL 报表包 ID] 已正确设置。如果是从代码管理器下载特定报表包的代码，或者代码是由 Adobe 技术顾问提供，一般都能正确设置此变量。

如果您要将 Analytics 与 Target 集成，则 JavaScript 包含文件必须置于页面底部。以下示例显示了 Analytics 代码的正确放置位置：

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3.
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

