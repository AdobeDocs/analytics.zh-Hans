---
title: getPageName
description: 从当前网站路径创建一个易于阅读的pageName。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe插件：getPageName

> [!IMPORTANT] 此插件由Adobe Consulting提供，旨在帮助您从Adobe Analytics中获得更多价值。 Adobe客户关怀部门不提供此插件的支持，包括安装或疑难解答。 如果您需要此插件的帮助，请与贵组织的客户经理联系。 他们可以安排与顾问的会议寻求帮助。

该 `getPageName` 插件可创建当前URL的易读、易用且格式化的版本。 如果您希望在报告中设置和理解 `pageName` 一个易于设置和理解的值，Adobe建议使用此插件。 如果已经有变量的命名结构（如通过数据层）, `pageName` 则不需要此插件。 当没有其他解决方案来设置变量时，最好使用该 `pageName` 变量。

## 使用Adobe Experience Platform Launch扩展安装插件

Adobe提供了一个扩展，允许您使用最常用的插件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击“目 [!UICONTROL 录] ”按钮
1. 安装和发布 [!UICONTROL Common Analytics插件扩展]
1. 如果尚未创建，请使用以下配置创建标有“初始化插件”的规则：
   * 条件：无
   * 事件：核心——载入的库（页面顶部）
1. 使用以下配置向上述规则添加操作：
   * 扩展：常见分析插件
   * 操作类型：初始化getPageName
1. 保存更改并发布到规则。

## 使用Launch自定义代码编辑器安装插件

如果您不想使用插件扩展，则可以使用自定义代码编辑器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 单击所需的属性。
1. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics扩 [!UICONTROL 展下的] “配置”按钮。
1. 使用自定 [!UICONTROL 义代码accordion展开“配置跟踪] ”，该面板显示“打 [!UICONTROL 开编辑器] ”按钮。
1. 打开自定义代码编辑器，并将下面提供的插件代码粘贴到编辑窗口中。
1. 保存更改并将其发布到Analytics扩展。

## 使用AppMeasurement安装插件

在实例化（使用）Analytics跟踪对象后，复制并粘贴AppMeasurement文件中的任意位置的以下代 `s_gi`码。 在您的实施中保留代码的注释和版本号可帮助Adobe解决任何潜在问题。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## 使用插件

该方 `getPageName` 法使用以下参数：

* **`si`**（可选，字符串）:插入到表示站点ID的字符串开头的ID。 此值可以是数字ID或友好名称。 如果未设置，则默认为当前域。
* **`qv`**（可选，字符串）:查询字符串参数的逗号分隔列表（如果在URL中找到）将添加到该字符串
* **`hv`**（可选，字符串）:在URL哈希中找到的以逗号分隔的参数列表，如果在URL中找到，则添加到字符串中
* **`de`**（可选，字符串）:用于拆分字符串各个部分的分隔符。 默认为管道(`|`)。

该方法返回一个包含URL的友好格式版本的字符串。 此字符串通常分配给变 `pageName` 量，但也可用于其他变量。

## 示例调用

### 示例#1

如果当前URL是……

```js
https://mail.google.com/mail/u/0/#inbox
```

...下面的代码运行……

```js
s.pageName = getPageName()
```

...s.pageName的最终值将为：

```js
s.pageName = "mail.google.com|mail|u|0";
```

### 示例#2

如果当前URL是……

```js
https://mail.google.com/mail/u/0/#inbox
```

...下面的代码运行……

```js
s.pageName = getPageName("gmail")
```

...s.pageName的最终值将为：

```js
s.pageName = "gmail|mail|u|0";
```

### 示例#3

如果当前URL是……

```js
https://www.google.com/
```

...下面的代码运行……

```js
s.pageName = getPageName()
```

...s.pageName的最终值将为：

```js
s.pageName = "www.google.com|home"
```

**注意**:当代码在不包含路径的URL上运行时，它将始终将“home”值添加到返回值的末尾

### 示例#4

如果当前URL是……

```js
https://www.google.com/
```

...下面的代码运行……

```js
s.pageName = getPageName("google","","","|")
```

...s.pageName的最终值将为：

```js
s.pageName = "google|home"
```

### 示例#5

如果当前URL是……

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...下面的代码运行……

```js
s.pageName = getPageName()
```

...s.pageName的最终值将为：

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

但是，如果以下代码改为运行……

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...s.pageName的最终值将为：

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## 从先前版本升级

getPageName插件的4.0+版不取决于要运行的Adobe Analytics的AppMeasurement对象（即“s”对象）的存在。  如果选择升级到此版本，请务必从调用中删除“s”对象的任何实例，以更改调用插件的代码。
例如，更改以下内容：

```js
s.pageName = s.getPageName();
```

...至此：

```js
s.pageName = getPageName();
```

## 版本历史

### 4.1（2019年9月17日）

* 将默认分隔符值更改为管道字符（从冒号+空格）。

### 4.0（2018年5月22日）

* 插件的完全重新分析／重写
