---
title: getQueryParam
description: 提取URL的查询字符串参数的值。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobe插件：getQueryParam

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该插 `getQueryParam` 件允许您提取URL中包含的任何查询字符串参数的值。 它可用于从登录页面URL提取内部和外部营销活动代码。 在提取搜索词或其他查询字符串参数时，它也很有价值。

此插件在解析复杂URL时提供强大功能，包括散列和包含多个查询字符串参数的URL。 如果您只有简单的查询字符串参数需要，Adobe建议使用Launch中的URL参数功能或AppMeasurement `Util.getQueryParam` 中包含的方法。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 对于要使用插件的任何启动规则，请添加一个具有以下配置的操作：
   * 扩展：常见分析插件
   * 操作类型：初始化addProductEvar
1. 保存更改并发布到规则

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getQueryParam` 法使用以下参数：

* **`qsp`**（必需）:要在URL中查找的查询字符串参数的逗号分隔列表。 它不区分大小写。
* **`de`**（可选）:多个查询字符串参数匹配时使用的分隔符。 默认为空字符串。
* **`url`**（可选）:用于从中提取查询字符串参数值的自定义URL、字符串或变量。 默认为`window.location`。

调用此方法会根据上述参数和URL返回一个值：

* 如果找不到匹配的查询字符串参数，则该方法返回空字符串。
* 如果找到匹配的查询字符串参数，则该方法返回查询字符串参数值。
* 如果找到匹配的查询字符串参数，但该值为空，则该方法返回 `true`。
* 如果找到多个匹配的查询字符串参数，则该方法返回一个字符串，每个参数值由参数中的字符串分 `de` 隔。

## 示例调用

### 示例#1

如果当前URL为：

```js
http://www.abc123.com/?cid=trackingcode1
```

以下代码将s.campaign设置为等于“trackingcode1”:

```js
s.campaign=s.getQueryParam('cid');
```

### 示例#2

如果当前URL为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

以下代码将s.campaign设置为等于“trackingcode1:123456”:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### 示例#3

如果当前URL为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

以下代码将s.campaign设置为等于“trackingcode1123456”:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### 示例#4

如果当前URL为：

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

以下代码将s.campaign设置为等于“123456”:

```js
s.campaign=s.getQueryParam('ecid');
```

### 示例#5

如果当前URL为：

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

以下代码将s.campaign设置为等于“123456”

```js
s.campaign=s.getQueryParam('ecid');
```

**** 注意：如果问号不存在，该插件会用问号替换Check的哈希字符的URL。  如果URL包含哈希字符前面的问号，则插件会将URL替换为“检查的哈希字符”的和号；

### 示例#6

如果当前URL为以下URL...

```js
http://www.abc123.com/
```

...如果按如下方式设置变量s.testURL:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

以下代码根本不会设置s.campaign:

```js
s.campaign=s.getQueryParam('cid');
```

但是，以下代码将s.campaign设置为等于“trackingcode1”:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**** 注意：第三个参数可以是代码将用来尝试在

以下代码将s.eVar2设置为等于“123456|trackingcode1|true|300”:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* 值123456来自s.testURL变量中的ecid参数
* trackingcode1的值来自s.testURL变量中的cid参数
* true的值来自s.testURL变量中散列字符后的位置参数的存在（但非值）

值300来自s.testURL变量中pos参数的值

## 版本历史

### 3.3（2019年9月24日）

* 绕过不必要的逻辑以减小代码大小

### 3.2（2018年5月15日）

* 将 `findParameterValue` 和 `getParameterValue` 函数移入函 `getQueryParam` 数

### 3.1（2018年5月10日）

* 修复了捕获无值查询字符串参数的问题

### 3.0（2018年4月16日）

* 点发行版（重新编译后，代码尺寸更小）。
* 为了可读性，将帮助 `findParameterValue` 程序函 `getParameterValue` 数重命名为和。
* 删除了添加参数以查找URL哈希中包含的参数的需求

### 2.5（2016年1月8日）

* 与H代码和AppMeasurement兼容(需要与AppMeasurement `s.pt` 一起使用)。

### 2.4

* 添加了 `h` 参数，允许代码查找在哈希()字符后找到的查询字符串`#`参数

### 2.3

* 修复了一个回归问题，该问题导致插件仅在跟踪代码后存在哈希时才起作用

### 2.2

* 现在从返回值中删除哈希字符（以及之后的所有内容）

### 2.1

* 与H.10代码兼容
