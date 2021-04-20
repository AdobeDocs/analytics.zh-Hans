---
description: 您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。
title: 区分引用相同链接 ID 和区域的多个链接
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 61%

---


# 区分引用相同链接 ID 和区域的多个链接

您可以通过以下方式区分链接：使用 s_objectID 变量来自定义链接 ID；自定义区域；以及自定义 AppMeasurement ActivityMap 模块文件。

例如，假设您拥有多个“购买”链接，且这些链接被 Activity Map 确认为属于同一个链接 ID 和区域：

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 代码示例 </th>
   <th colname="col2" class="entry"> 链接 ID </th>
   <th colname="col3" class="entry"> 区域 </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    推荐面板<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    推荐面板<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

如何自定义网页和标签，以区分这些链接的值？您有三种选项：您可以自定义链接 ID、自定义区域，或自定义 AppMeasurement ActivityMap 模块文件。

## 使用 s_objectID 来自定义链接 ID  {#section_01B0D463397B4837B2D46F087A6E5937}

通过为页面上的链接或链接位置创建唯一的对象ID `s_objectID`，您可以改进Activity Map跟踪或使用Activity Map报告链接类型或位置，而不是链接URL。 单击[此处](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/vars/page-vars/page-variables.html)，以了解有关 变量的更多信息。`s_objectID`

>[!IMPORTANT]
>
>请注意，在Activity Map中使用`s_objectID`时，需要尾随分号(`;`)。
<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> 代码示例 </th>
   <th colname="col2" class="entry"> 链接 ID </th>
   <th colname="col3" class="entry"> 区域 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    推荐面板<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    推荐面板<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## 自定义区域 {#section_6B1EF302573B445DBAF44176D0A12DB9}

您可以通过确保每个“购买”链接都定义了自己的区域来自定义区域。 为此，请向每个“Buy”锚记的父项之一添加一个`"id"`参数。

>[!NOTE]
>您并不严格限于作为区域标识符的`"id"`参数。 您还可以使用JavaScript变量`"s.ActivityMap.regionIDAttribute"`设置自己的标识符。
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> 代码示例 </th>
   <th colname="col2" class="entry"> 链接 ID </th>
   <th colname="col3" class="entry"> 区域 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
    购买<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    区域a<br/>
     <br/>
     <br/>
    区域b<br/>
     <br/>
     <br/>
    区域c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## 自定义 AppMeasurement ActivityMap 模块文件 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
请务必测试修改后的代码，以确保修改后的代码能够正常运行。Adobe 对于修改后的代码的行为概不负责。

以下是一些&#x200B;**通用**&#x200B;链接/区域函数的示例，您可以将这些函数（以修改后的形式）放入您的 AppMeasurement.js 文件。

```
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

在调用`s.tl()`期间传递`linkName`。

```
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
