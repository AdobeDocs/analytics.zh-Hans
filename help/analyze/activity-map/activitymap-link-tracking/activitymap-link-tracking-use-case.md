---
description: 您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。
seo-description: 您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。
seo-title: 区分引用相同链接ID和区域的链接
solution: Analytics
title: 区分引用相同链接ID和区域的链接
topic: Activity Map
uuid: f2da0cda-a33 b-4a12-8d99-1f58386 d6 d30
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# 区分引用相同链接ID和区域的链接

您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。

例如，假设您拥有多个“购买”链接，且这些链接被 Activity Map 确认为属于同一个链接 ID 和区域：

<table id="table_3020E2C0175D455C84E794CF51BE5A93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码样例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 区域 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code>&lt; div id=“推荐面板”&gt;
&lt; div&gt;
&lt; a href="product1.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a href="product2.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a href="product3.html"&gt;购买&lt;/a&gt;
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>购买 <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>推荐面板 <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> </td> 
  </tr> 
 </tbody> 
</table>

如何自定义网页和标签，以区分这些链接的值？您有三种选项：您可以自定义链接 ID、自定义区域，或自定义 AppMeasurement ActivityMap 模块文件。

## 使用 s_objectID 来自定义链接 ID {#section_01B0D463397B4837B2D46F087A6E5937}

通过为链接或页面上的链接位置创建唯一对象 ID，您可以改善 Activity Map 跟踪功能，或使用 Activity Map（而非链接 URL）来报告链接的类型或位置。单击[此处](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html)，以了解有关 s_objectID 变量的更多信息。

>[!IMPORTANT]
>
>请注意，在活动地图中使用s_ objectID时，需要结尾分号(；)。

<table id="table_9439A5F320304E439A19842CF3EBA456"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 代码样例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 区域 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>&lt; div id=“推荐面板”&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product1'；“href=”product1.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product2'；“href=”product2.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div&gt;
&lt; a onClick="s_ objectID='Product3'；“href=”product3.html"&gt;购买&lt;/a&gt;
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product2 </p> <p> </p> <p> </p> <p>Product3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> <p> </p> <p>推荐面板 </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自定义区域 {#section_6B1EF302573B445DBAF44176D0A12DB9}

您可以通过确保各个“购买”链接都定义了自己的区域，来自定义区域。要完成此操作，请将“id”参数添加到各个“购买”锚标记的父项之一。

>[!NOTE]
>
>您并不严格局限于“id”参数作为区域标识符。您还可以使用JavaScript变量“s. ActivityMap. regionIDAttribute”设置自己的标识符。

<table id="table_250DB52A869C466B942517BABA1C287B"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 代码样例 </th> 
   <th colname="col2" class="entry"> 链接 ID </th> 
   <th colname="col3" class="entry"> 区域 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>&lt; div id=“推荐面板”&gt;
&lt; div id=“region a”&gt;
&lt; a href="product1.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div id=“region b”&gt;
&lt; a href="product2.html"&gt;购买&lt;/a&gt;
&lt;/div&gt;
&lt; div id=“region c”&gt;
&lt; a href="product3.html"&gt;购买&lt;/a&gt;
&lt;/div&gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> <p> </p> <p> </p> <p>购买 </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自定义 AppMeasurement ActivityMap 模块文件 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>请确保测试修改过的代码，以确保其正常工作。Adobe 对于修改后的代码的行为概不负责。

以下是** generic**链接/地区函数的几个示例，您可以在AppMeasurement. js文件中包含(修改的表单)。

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

