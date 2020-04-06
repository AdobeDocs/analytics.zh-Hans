---
description: 您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。
title: 区分引用相同链接 ID 和区域的多个链接
topic: Activity map
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 区分引用相同链接 ID 和区域的多个链接

您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。

例如，假设您有多个“购买”链接，这些链接由活动图在同一链接ID和区域下标识：

<table id="table_3020E2C0175D455C84E794CF51BE5A93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码示例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 地区 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>购买 <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>推荐面板 <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> </td> 
  </tr> 
 </tbody> 
</table>

如何自定义网页和标记以区分这些链接的值？ 您有三种选择：您可以自定义链接ID，或自定义区域，或自定义AppMeasurement ActivityMap模块文件。

## 使用s_objectID自定义链接ID {#section_01B0D463397B4837B2D46F087A6E5937}

通过为链接或页面上的链接位置创建唯一的对象ID，您可以改进活动图跟踪或使用活动图报告链接类型或位置，而不是链接URL。 单 [击此处](https://marketing.adobe.com/resources/help/zh_CN/sc/implement/s_objectID.html) ，可了解有关s_objectID变量的更多信息。

>[!IMPORTANT]
>
>请注意，在 Activity Map 中使用 s_objectID 时，需要以分号 (;) 结尾。

<table id="table_9439A5F320304E439A19842CF3EBA456"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 代码示例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 地区 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>产品2 </p> <p> </p> <p> </p> <p>产品3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自定义区域 {#section_6B1EF302573B445DBAF44176D0A12DB9}

您可以通过确保每个“购买”链接都定义了自己的“区域”来自定义该区域。 为此，请向每个“购买”锚标记的父项之一添加“id”参数。

>[!NOTE] 您并非必须使用“id”参数作为区域标识符。您也可以使用 JavaScript 变量“s.ActivityMap.regionIDAttribute”来设置自己的标识符。

<table id="table_250DB52A869C466B942517BABA1C287B"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 代码示例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 地区 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>区域 <p> </p> <p> </p> <p>区域b </p> <p> </p> <p> </p> <p>区域c </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自定义AppMeasurement ActivityMap模块文件 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>请务必测试修改后的代码，以确保修改后的代码能够正常运行。Adobe 对于修改后的代码的行为概不负责。

以下是一些**通用**链接/区域函数的示例，您可以将这些函数（以修改后的形式）放入 AppMeasurement.js 文件中。

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

linkName 是在调用 s.tl 期间被传递。

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```

